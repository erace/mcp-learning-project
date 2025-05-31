# MCP Usage Patterns - Complete Guide

## Filesystem MCP vs SQLite MCP - When to Use What

### 🗂️ Filesystem MCP - Best For:

#### **Primary Use Cases:**
- **Session Documentation**: README files, logs, context handoff documents
- **Project Assets**: Templates, scripts, configuration files
- **Unstructured Content**: Notes, drafts, research documents
- **File Organization**: Creating directory structures, managing project files
- **Context Preservation**: Master context files, session summaries

#### **Strengths:**
- ✅ **Universal File Support**: Any file type (markdown, JSON, scripts, images)
- ✅ **Human Readable**: Files can be opened in any editor
- ✅ **Version Control Ready**: Works perfectly with Git
- ✅ **No Schema Required**: Flexible, no predefined structure
- ✅ **Direct Access**: Files persist outside of Claude environment

#### **When to Choose Filesystem:**
```
If your data is primarily:
- Documents and text content
- Templates and configurations  
- Project files and assets
- Anything humans need to read/edit directly
- Content that needs version control
```

#### **Example Scenarios:**
- Creating project documentation
- Storing session logs and context
- Managing templates and configurations
- Building file-based workflows
- Organizing research and notes

---

### 🗄️ SQLite MCP - Best For:

#### **Primary Use Cases:**
- **Structured Data**: Tables, relationships, metrics
- **Pattern Tracking**: Learning patterns, decision frameworks
- **Queryable Knowledge**: Data that needs filtering, sorting, analysis
- **Metrics and Ratings**: Performance tracking, comparisons
- **Lookup Tables**: Reference data, configurations

#### **Strengths:**
- ✅ **SQL Queries**: Powerful filtering, sorting, aggregation
- ✅ **Data Relationships**: Foreign keys, joins, normalization
- ✅ **Atomic Operations**: ACID compliance, data integrity
- ✅ **Performance**: Fast queries on large datasets
- ✅ **Structure Validation**: Schema enforcement, data types

#### **When to Choose SQLite:**
```
If your data needs:
- Querying and filtering
- Relationships between entities
- Aggregation and analysis
- Structured validation
- Performance with large datasets
```

#### **Example Scenarios:**
- Tracking MCP server capabilities and ratings
- Storing learning session metrics
- Building decision matrices
- Managing lookup tables and references
- Analyzing patterns and trends

---

### 🎯 Decision Framework

#### Use **Filesystem MCP** when:
- [ ] Content is primarily text/documents
- [ ] Humans need to read/edit files directly
- [ ] No complex querying needed
- [ ] File-based organization makes sense
- [ ] Version control is important

#### Use **SQLite MCP** when:
- [ ] Data has clear structure/schema
- [ ] Need to query, filter, or analyze
- [ ] Relationships between data exist  
- [ ] Performance with large data matters
- [ ] Data validation is important

#### Use **Both Together** when:
- [ ] Building comprehensive systems
- [ ] Need both documents AND structured data
- [ ] Files contain metadata worth tracking
- [ ] Complex projects with multiple data types

---

### 📋 Real-World Usage Patterns

#### **Pattern 1: Learning System (Current Project)**
```
Filesystem: Session logs, templates, documentation
SQLite: MCP ratings, patterns, session metrics
Result: Complete learning tracking system
```

#### **Pattern 2: Software Project**
```
Filesystem: Code files, configs, README, docs
SQLite: Bug tracking, performance metrics, feature flags
Result: Full project management system
```

#### **Pattern 3: Research Project**
```
Filesystem: Papers, notes, drafts, references
SQLite: Citation tracking, topic analysis, progress metrics
Result: Structured research management
```

#### **Pattern 4: Business Operations**
```
Filesystem: Reports, templates, procedures
SQLite: KPIs, customer data, financial metrics
Result: Complete business intelligence system
```

---

### ⚠️ Common Anti-Patterns

#### **Don't Use Filesystem For:**
- ❌ Data that needs frequent querying
- ❌ Structured data with relationships
- ❌ Metrics and analytics
- ❌ Data that needs validation
- ❌ Large datasets requiring performance

#### **Don't Use SQLite For:**
- ❌ Large text documents or articles
- ❌ Binary files (images, videos)
- ❌ Simple key-value storage
- ❌ Data without clear structure
- ❌ Content humans need to edit directly

---

### 🚀 Context Preservation Strategies

#### **Filesystem Approach:**
```markdown
# master-context.md
## Current Project State
- Phase: [Current phase]
- Last Updated: [Date]
- Key Decisions: [List]
- Next Steps: [Priorities]

## Quick Restart
- Key files: [List with purposes]
- Important commands: [Commands]
- Context files: [Handoff documents]
```

#### **SQLite Approach:**
```sql
-- Query current project state
SELECT * FROM project_status WHERE active = 1;

-- Get recent decisions
SELECT * FROM decisions 
WHERE date >= date('now', '-7 days')
ORDER BY importance DESC;

-- Check next priorities
SELECT * FROM tasks 
WHERE status = 'next' 
ORDER BY priority DESC;
```

#### **Hybrid Approach:**
- **Master context file** (filesystem) references key database IDs
- **Database records** link to relevant files
- **Session handoffs** update both systems
- **Quick restart** queries database + reads key files

---

### 💡 Pro Tips for Your Big Project

1. **Start with Filesystem** for initial organization
2. **Add SQLite** when patterns emerge that need querying
3. **Use consistent naming** between files and database records
4. **Create linking strategies** (file paths in database, IDs in files)
5. **Regular context snapshots** in both systems
6. **Design for handoffs** from day one

This hybrid approach will solve your "chat memory limit" problem completely - you'll have both human-readable context files AND queryable structured data for any project scale.
