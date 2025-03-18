## 📂 Understanding Jenkins File Structure

Once Jenkins is set up, it maintains all of its configurations, jobs, and settings inside `/var/lib/jenkins`. Here’s a breakdown of its folder structure:
If you run jenkins docker way then the folder is /var/jenkins_home
```
/var/lib/jenkins
│-- config.xml      # Main Jenkins configuration file
│-- plugins/        # Installed plugins
│-- jobs/           # Each job has its own folder
│   │-- <job-name>/ 
│   │   │-- config.xml  # Job configuration
│   │   │-- builds/     # Build history
│   │   │-- workspace/  # Working directory for the job
│-- nodes/          # Optional, for distributed builds
│-- credentials/    # Securely stored credentials
```

### 🔍 Key Takeaways:
- **config.xml**: This is the heart of Jenkins; it defines global settings.
- **plugins/**: Stores all Jenkins plugins.
- **jobs/**: Each job gets its own directory, containing configuration, build history, and workspace.
- **nodes/** (Optional): Used if Jenkins is running with multiple nodes.
- **credentials/**: Secure storage for secrets and access keys.

This structure helps in **backup, migration, and troubleshooting** like a pro! 💡
