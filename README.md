# Capacity-Sharing-and-Assignment-Decisions-in-Container-Truck-Platforms
Numerical instances for Capacity Sharing and Assignment Decisions in Container Truck Platforms
Source: Capacity Sharing and Assignment Decisions in Container Truck Platforms

K = number of vehicles / drivers in the instance
R = number of tasks / orders in the instance
S = number of vehicle states (S = 3)
R/K ratio = R/K (instance scale ratio)

Total_R / Total_K / Total_station = 500 / 500 / 50
  (overall parameter pool size; all instances are sampled from this pool)
Number of sampling groups = 10,000
  (pre-generated vehicle/task subset combinations, indexed by "Sampled Group No.")
Commission Rate = 0.30
  (platform commission; q_r + P_r = total reward of task r)

The format of these data files is:

header lines (comment, start with "#"): instance ID, Index, Sampled Group No.,Experiment Seed, Commission Rate, K, R, S
[mapping] vehicle new-index → global-index (K entries):
  local vehicle index k (k = 0, ..., K-1) → global vehicle index in the 500-vehicle pool
[mapping] task new-index → global-index (R entries):
  local task index r (r = 0, ..., R-1) → global task index in the 500-task pool
[g_k original travel cost of vehicle] (K entries):
  for each vehicle k: g_k = original travel cost of vehicle k
[l_k vehicle capacity] (K entries):
  for each vehicle k: l_k = capacity of vehicle k
[C_r task capacity demand] (R entries):
  for each task r: C_r = capacity demand of task r
[q_r reward to vehicle] (R entries):
  for each task r: q_r = reward paid to the vehicle that serves task r
[P_r platform profit] (R entries):
  for each task r: P_r = platform profit collected from task r
[d_kr (row k, col r)] (K × R matrix):
  d_kr = distance between vehicle k and task r  (0 in the performance-experiment instances)
[W_kr (row k, col r)] (K × R matrix):
  W_kr = original travel workload of vehicle k assigned to task r  (0 in the performance-experiment instances)
[l_ks (row k, col s)] (K × S matrix):
  for each vehicle k and state s: l_ks = remaining capacity of vehicle k in state s
[d_ksr s=0 (row k, col r)] (S blocks, each K × R):
  for each state s: d_ksr = distance between vehicle k (in state s) and task r
[w_ksr s=0 (row k, col r)] (S blocks, each K × R):
  for each state s: w_ksr = q_r / (d_ksr - g_k), the workload ratio of assigning task r to
  vehicle k in state s .
