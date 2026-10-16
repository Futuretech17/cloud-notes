## Lab: Linux System Architecture, Advanced Administration & Automation Pipelines

- **Built:** 
  - **Standardized File System Mapping:** Explored and mapped the core blueprint of the Linux File System Hierarchy Standard (FHS), tracing system workflows across root (`/`), configuration paths (`/etc`), system resources (`/usr`), dynamic logs (`/var`), and service data directories (`/srv`).
  - **Enterprise User Infrastructure:** Orchestrated an enterprise-grade Role-Based Access Control (RBAC) matrix by creating departmental groups (`dev-group`, `senior-group`) and mapping multi-tier users (`alex-analyst`, `bob-analyst`, `sarah-senior-analyst`).
  - **Automated Service Environment:** Engineered a mock production data environment under `/srv/app_data` utilizing isolated system service accounts (`collector-bot`, `analyzer-engine`) to simulate headless application interactions.
  - **Cross-Platform Virtualization Architecture:** Staged and cross-examined the behavioral differences between standalone Virtual Machines (VMs) and Windows Subsystem for Linux (WSL) environments.
  - **Shell Automation Pipelines:** Developed standalone Bash and Zsh automation scripts (`.sh`) utilizing input/output file descriptor redirection (`>` and `>>`) to orchestrate live system processes.

- **Broke:** 
  - **Live Permission Deadlocks:** Witnessed a production-level pipeline crash firsthand when the `analyzer-engine` bot hit a critical `Permission Denied` error due to default file birth constraints.
  - **Shell Syntax Exceptions:** Triggered an interpretative shell failure (**Unexpected EOF**) by creating unclosed quotation literals inside active code paths.
  - **Missing Dependency Exceptions:** Encountered real-time environment validation warnings by attempting to force a user shell instance (`/bin/zsh`) before the package was physically compiled on the host system.

- **Learned:** 
  - **Multi-Tier File Discovery Tools:** Mastered the unique engineering use cases for system location tools: **`find`** for real-time metadata searches (size, date, user tags), **`locate`** for instantaneous indexing database scans (`updatedb`), and **`which`/`type`** for pinpointing executable program paths across the system `$PATH`.
  - **Heavy Log Telemetry (`grep` & `less`):** Learned how to parse massive gigabyte-scale logs efficiently without causing memory page lockups using line-by-line streaming, employing context window flags (`-A`, `-B`, `-C`) and visual navigation markers (`/` in `less`).
  - **The Mathematical Laws of Birth (`umask`):** Mastered how the kernel subtracts system stencils/masks from open file (`666`) baselines to strip write privileges, and learned to override this at runtime using `umask 0002` to prevent permission deadlocks.
  - **Directory Access Checkpoints:** Dissected the physical file system hierarchy—discovering that directory execute permissions (`x`) act as linear checkpoints from root (`/`) down to sub-folders, regardless of lower-tier privileges.
  - **Advanced Directory Governance (SGID & Sticky Bit):** Understood how to use the **SGID bit (`g+s`)** to force directory-level group inheritance, and how the **Sticky Bit (`+t`)** creates a secure mailbox drop room where users are blocked from deleting each other's files.
  - **The Architecture of Link Pointers:** Demystified **Symlinks** (path-based shortcuts that cross hard drives and directories) vs. **Hard Links** (direct inode address duplications used for space-saving incremental snapshots).
  - **Account Lifecycles & Security Compliance:** Evaluated corporate offboarding workflows, learning why renaming accounts leaks legacy numeric User IDs (UIDs) to new hires, and how to safely lock, back up, and purge users via `userdel -r`.
  - **Privilege Escalation Mitigation:** Examined how hackers hijack unprivileged bots to inject malicious scripts into open `777` directories, locking down the system by separating script execution privileges from data write access.


  ## Lab: Linux System Architecture, Advanced Administration & Automation Pipelines

- **Built:** 
  - **Process-to-PID Mappings:** Manually constructed pipeline filters (`ps aux | grep <name>`) to isolate specific processes from hundreds of system lines and extract their active Process IDs (PIDs).
  - **Custom Background Service Blueprints:** Dissected a structural `systemd` unit file blueprint (`webapp.service`) isolating dependency targets (`After=network.target`), establishing restricted runtime boundaries (`User=www-data`), and configuring automated self-healing crash policies (`Restart=on-failure / RestartSec=5`).

- **Broke:** 
  - **Port Binding Conflicts:** Troubleshooted a simulated service crash (`failed / exit-code`) inside `systemctl` triggered by a legacy background testing script (PID 4102) capturing an identical networking socket (Port 8080).

- **Learned:** 
  - **Granular Process Evaluation (`ps`):** Mastered process observation across different time and structural models, leveraging BSD syntax (`ps aux`) for user resource consumption snapshots and standard syntax (`ps -ef`) for parent-child relationship (`PPID`) tree tracking.
  - **Real-Time Telemetry Dashboards (`top` vs `htop`):** Contrasted static snapshots with live system monitoring, utilizing standard `top` for automated resource ranking and modern `htop` for visual, color-coded CPU/RAM core mapping and interactive keyboard navigation.
  - **Signal Aggression Controls (`kill` vs `pkill`):** Learned to differentiate between graceful termination requests (**`SIGTERM / Signal 15`**) that allow apps to safely save data, and un-catchable kernel-level process destruction (**`SIGKILL / Signal 9`**), executing them via explicit numerical PIDs (`kill`) or broad string name patterns (`pkill`).
  - **Init Engine Lifecycle Control (`systemctl`):** Decoupled transient process execution states from persistent boot layers, utilizing `start`/`stop`/`restart` to manipulate the present runtime state, and `enable`/`disable` to dictate future boot configurations via target hooks (`multi-user.target`).
  - **Central System Logging Systems (`journalctl`):** Mapped unified Linux log infrastructure directly to its cross-platform equivalent (Windows Event Viewer), mastering targeted unit isolation flags (`-u`), real-time live telemetry streaming (`-f`), and temporal time-machine filtering (`--since`).
  - **Process-Port Limitations:** Identified architectural limitations of process monitors, discovering that tools like `htop` handle hardware metrics but omit network socket/port allocations, which require specialized networking telemetry tools.


## Lab: Setup & Core Linux Fundamentals (2026-10-13 to 2026-10-16)

- **Built:** 
  - A solid core foundation in navigation and file management across the Linux file system.
  - Multi-stage, complex command pipelines (`|`) designed to inspect, sort, clean, and extract specific metrics from raw system files.
  - A real-time data parser for an AWS billing dataset (`aws_costs.csv`) to compute targeted operational costs.
  - Custom conditional alert logic (`&&` and `||`) behaving like text-based automated workflows directly inside the terminal wrapper.

- **Broke:** 
  - Ran into stream bottlenecks where `awk` sat waiting indefinitely because data streams were split by conditional logic (`&&`) rather than being properly piped (`|`).
  - Misordered code blocks in field processors, learning firsthand that interpreters execute scripts from left-to-right strictly.
  - Wrestled with data syntax anomalies, tracking down minor typos (`ech` vs `echo`) that instantly halt terminal execution workflows.

- **Learned:** 
  - **Text Dissection:** Mastered navigating and filtering massive streams of noisy string data dynamically using `grep`, `sed`, `cut`, `sort`, and `uniq`.
  - **Stream Internals:** Deeply understood how the kernel reads data fields—learning why tools like `wc` evaluate structured files (like `/etc/passwd`) based purely on whitespaces rather than visual strings.
  - **In-Place Mutation:** Learned how to perform non-destructive global edits across system and application config environments natively with `sed -i`.
  - **Engineering Mindset:** Embraced the reality that breaking paths, causing terminal hangs, and debugging unexpected outputs is the exact workflow of a practicing Cloud Engineer.

