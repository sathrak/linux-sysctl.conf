# KERNEL TUNING #

# Maximizing I/O Throughput
# Minimal preemption granularity for CPU-bound tasks:
# (default: 1 msec#  (1 + ilog(ncpus)), units: nanoseconds)
kernel.sched_min_granularity_ns = 10000000

# SCHED_OTHER wake-up granularity.
# (default: 1 msec#  (1 + ilog(ncpus)), units: nanoseconds)
#
# This option delays the preemption effects of decoupled workloads
# and reduces their over-scheduling. Synchronous workloads will still
# have immediate wakeup/sleep latencies.
kernel.sched_wakeup_granularity_ns = 15000000

# Maximum System V IPC message size in bytes.
# default(8192)
kernel.msgmax=8192

# Number of system V IPC system-wide semaphore identifiers.
kernel.sem=250 256000 32 1024

# Maximum number of bytes on a single System V IPC message queue.
kernel.msgmnb=65536

# Displays the maximum number of threads possible system-wide.
kernel.threads-max = 131072 

# Maximum number of threads allowed in each process.
kernel.max_thread_proc = 2048

# Increase size of file handles and inode cache
fs.file-max = 2097152

# Do less swapping
vm.swappiness = 10
vm.dirty_ratio = 60
vm.dirty_background_ratio = 2

# Sets the time before the kernel considers migrating a proccess to another core
kernel.sched_migration_cost_ns = 5000000

# Group tasks by TTY
#kernel.sched_autogroup_enabled = 0

### GENERAL NETWORK SECURITY OPTIONS ###

# Number of times SYNACKs for passive TCP connection.
net.ipv4.tcp_synack_retries = 2

# Allowed local port range
net.ipv4.ip_local_port_range = 2000 65535

# Protect Against TCP Time-Wait
net.ipv4.tcp_rfc1337 = 1

# Control Syncookies
net.ipv4.tcp_syncookies = 1

# Decrease the time default value for tcp_fin_timeout connection
net.ipv4.tcp_fin_timeout = 15

# Decrease the time default value for connections to keep alive
net.ipv4.tcp_keepalive_time = 300
net.ipv4.tcp_keepalive_probes = 5
net.ipv4.tcp_keepalive_intvl = 15

### TUNING NETWORK PERFORMANCE ###

# Default Socket Receive Buffer
net.core.rmem_default = 31457280

# Maximum Socket Receive Buffer
net.core.rmem_max = 33554432

# Default Socket Send Buffer
net.core.wmem_default = 31457280

# Maximum Socket Send Buffer
net.core.wmem_max = 33554432

# Increase number of incoming connections
net.core.somaxconn = 65535

# Increase number of incoming connections backlog
net.core.netdev_max_backlog = 65536

# Increase the maximum amount of option memory buffers
net.core.optmem_max = 25165824

# Increase the maximum total buffer-space allocatable
# This is measured in units of pages (4096 bytes)
net.ipv4.tcp_mem = 786432 1048576 26777216
net.ipv4.udp_mem = 65536 131072 262144

# Increase the read-buffer space allocatable
net.ipv4.tcp_rmem = 8192 87380 33554432
net.ipv4.udp_rmem_min = 16384

# Increase the write-buffer-space allocatable
net.ipv4.tcp_wmem = 8192 65536 33554432
net.ipv4.udp_wmem_min = 16384

# Increase the tcp-time-wait buckets pool size to prevent simple DOS attacks
net.ipv4.tcp_max_tw_buckets = 1440000
net.ipv4.tcp_tw_recycle = 1
net.ipv4.tcp_tw_reuse = 1

# This will enusre that immediatly subsequent connections use these values. 
net.ipv4.route.flush=1
