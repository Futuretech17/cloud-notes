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
