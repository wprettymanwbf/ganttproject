# Microsoft Project Compatibility Guide

## Overview

GanttProject is a free, open-source project management tool that provides many features similar to Microsoft Project. This document helps Microsoft Project users understand how GanttProject compares and how to migrate their projects.

## Feature Comparison

### Core Features (Fully Supported)

✅ **Task Management**
- Task hierarchy and nested tasks
- Task dependencies (Finish-to-Start, Start-to-Start, Finish-to-Finish, Start-to-Finish)
- Milestones
- Task duration and scheduling
- Task priorities (Lowest, Low, Normal, High, Highest)
- Task completion percentage
- Task notes/description
- Critical path calculation

✅ **Gantt Chart**
- Visual timeline representation
- Dependency arrows
- Progress tracking
- Baselines for tracking changes
- Customizable colors and shapes

✅ **Resource Management**
- Resource assignment to tasks
- Multiple resources per task
- Resource roles
- Resource standard pay rates
- Resource calendars with custom working hours
- Resource vacation/time off tracking

✅ **Cost Tracking**
- Task cost calculation
- Manual and calculated cost modes
- Resource-based cost calculation
- Project-level budget tracking (NEW!)

✅ **Calendar Management**
- Custom working time calendars
- Holidays and non-working days
- Different calendars for different resources
- Weekend configuration

✅ **File Format Interoperability**
- Import from Microsoft Project (.mpp, .mpx, .xml)
- Export to Microsoft Project XML format
- Excel import/export
- CSV import/export
- PDF export

✅ **Reporting**
- Export to PDF, HTML, PNG
- Customizable Gantt chart views
- Resource load charts
- PERT chart generation

### Features with Differences

⚠️ **Resource Leveling**
- Microsoft Project: Automated resource leveling algorithms
- GanttProject: Manual resource management, no automatic leveling

⚠️ **Budgeting**
- Microsoft Project: Comprehensive budget tracking with variance analysis, earned value management
- GanttProject: Project-level budget field available (as of latest version), task-level cost calculation, basic budget tracking (no automated variance analysis yet)

⚠️ **Custom Fields**
- Microsoft Project: Extensive custom field support with formulas
- GanttProject: Basic custom property support for tasks and resources

⚠️ **Collaboration**
- Microsoft Project: Built-in cloud collaboration, Teams integration
- GanttProject: WebDAV support, GanttProject Cloud (commercial service)

### Features Not Yet Supported

❌ **Portfolio Management**
- Multi-project dashboards
- Cross-project resource allocation
- Program-level reporting

❌ **Document Attachments**
- Direct file attachments to tasks
- Document management integration

❌ **Advanced Reporting**
- Custom report builder
- Burndown charts
- Earned value analysis
- Resource histograms

❌ **Workflow Automation**
- Automated notifications
- Custom workflows
- Scripting/macros

## Migration Guide

### Importing from Microsoft Project

1. **Save your Microsoft Project file** in one of these formats:
   - `.mpp` (Microsoft Project binary format)
   - `.mpx` (Microsoft Project Exchange format)
   - `.xml` (Microsoft Project XML format - recommended for best compatibility)

2. **Open GanttProject** and go to: `Project → Import → Microsoft Project`

3. **Select your file** and configure import options:
   - **Resource Merge Option**: Choose how to handle resources that might already exist
   - **Import Calendar**: Choose whether to import the project calendar

4. **Review imported data**:
   - Task hierarchy and dependencies
   - Resource assignments
   - Task dates and durations
   - Notes and descriptions

### Common Mapping

| Microsoft Project | GanttProject |
|-------------------|--------------|
| Task | Task |
| Summary Task | Task with subtasks |
| Milestone | Milestone (duration = 0) |
| Resource | Human Resource |
| Task Dependency | Task Dependency |
| Baseline | Baseline |
| Calendar | Calendar |
| Cost | Cost (manual or calculated) |
| Priority | Priority (5 levels) |
| % Complete | Completion Percentage |

### Keyboard Shortcuts

GanttProject supports many keyboard shortcuts for efficient task management:

- `Ctrl+N`: New project
- `Ctrl+O`: Open project
- `Ctrl+S`: Save project
- `Ctrl+Z`: Undo
- `Ctrl+Y`: Redo
- `Insert`: New task
- `Delete`: Delete selected task
- `Ctrl+D`: Task properties
- `Ctrl+L`: Link tasks (create dependency)
- `Alt+Up/Down`: Move task up/down in the hierarchy
- `Alt+Left/Right`: Indent/outdent task

### Tips for Microsoft Project Users

1. **Task Dependencies**: Use the dependency dialog (`Ctrl+L`) or drag between tasks in the Gantt chart

2. **Resource Assignment**: Right-click a task and select "Assign Resources" or use the Resources tab in task properties

3. **Baselines**: Save a baseline before making changes via `Project → Baselines → Save`

4. **Critical Path**: Enable via `View → Critical Path` to highlight critical tasks

5. **Filtering**: Use the filter dropdown in the toolbar to show/hide specific tasks

6. **Exporting**: Export to Microsoft Project XML for sharing with MS Project users via `Project → Export → Microsoft Project`

7. **Printing**: Export to PDF for printing via `File → Export → PDF`

## Workflow Differences

### Creating a New Project

**Microsoft Project:**
1. File → New
2. Enter project information
3. Set project start date
4. Begin adding tasks

**GanttProject:**
1. Project → New
2. Enter project name, organization, and description
3. Project properties set the start date implicitly with first task
4. Begin adding tasks

### Resource Allocation

**Microsoft Project:**
- Resource Sheet view for managing resources
- Resource allocation via Resource Names column

**GanttProject:**
- Resources tab at the bottom
- Add resources first, then assign via task properties or Resources panel

### Tracking Progress

**Microsoft Project:**
- Update Tasks dialog
- Timeline view

**GanttProject:**
- Edit task completion percentage directly in task list
- Progress shown on Gantt bars
- Use baselines to compare original vs. current plan

### Setting a Project Budget

**Microsoft Project:**
- Project Information dialog → Budget field
- Use Budget resources for detailed tracking
- Earned Value analysis

**GanttProject:**
- Project → Properties → Budget field
- Set overall project budget
- Compare against task costs manually or via reports
- Future versions may include automated budget variance analysis

## Best Practices for Migration

1. **Clean Your Data**: Before importing, remove any Microsoft Project-specific customizations that might not translate well

2. **Use XML Format**: Export from Microsoft Project to XML format for the most reliable import

3. **Import in Stages**: For large projects, consider breaking them into phases and importing separately

4. **Verify Dependencies**: After import, review task dependencies to ensure they were preserved correctly

5. **Reassign Resources**: Double-check resource assignments as some complex allocation patterns may not import perfectly

6. **Set Up Calendars**: Configure working time calendars to match your organization's schedule

7. **Create a New Baseline**: After importing and verifying, create a new baseline in GanttProject

8. **Set Project Budget**: Use the new budget field in Project Properties to track overall project budget

## Frequently Asked Questions

**Q: Can I open .mpp files directly?**
A: Yes, GanttProject can import .mpp files. For best results, export to XML from Microsoft Project.

**Q: Will all my custom fields be preserved?**
A: GanttProject supports custom properties but the mapping may not be perfect. Review custom fields after import.

**Q: Can I collaborate with Microsoft Project users?**
A: Yes, by exchanging files in Microsoft Project XML format. Both tools can read and write this format.

**Q: Is there a cloud version like Project for the Web?**
A: GanttProject Cloud is available as a commercial service for cloud storage and collaboration.

**Q: Can I use GanttProject with Microsoft 365?**
A: GanttProject is a standalone desktop application. You can store files on OneDrive or SharePoint via WebDAV.

**Q: How do I get support?**
A: Visit https://www.ganttproject.biz for documentation, forums, and support options.

## Additional Resources

- GanttProject Website: https://www.ganttproject.biz
- User Manual: https://www.ganttproject.biz/help
- GitHub Repository: https://github.com/bardsoftware/ganttproject
- GanttProject Cloud: https://ganttproject.cloud

## Contributing

GanttProject is open source! If you'd like to help improve Microsoft Project compatibility:

1. Report issues or suggest features on GitHub
2. Contribute code improvements
3. Help improve documentation
4. Share your migration experiences

---

*Last updated: January 2026*
*GanttProject Version: 3.3+*
