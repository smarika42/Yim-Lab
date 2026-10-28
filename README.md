**Yim-Lab** <br><br>
All Data Analysis for Yim Lab at Texas Tech University and its results. <br>

**Rows & Columns** <br><br>
1 index <br>
2 date <br>
3 time <br>
4 status (1 = valid, 51 = no data received) <br>
5 extras <br>
6 monitor <br>
7 tube # (0 on monitor rows) <br>
8 data type <br>
9 unused <br>
10 light sensor (1 = on) <br>
11-42  one value per tube (32 tubes) <br>

**Abbreviations** <br> <br>

MT  moves total (beam-to-beam movements)  <- default activity measure <br>
CT  counts total (beam entries) <br>
D12 / D34  % of the minute spent in the left / right half of the tube (sum = 100)<br>
L12 / L34  latency (quarter-s) to first count in the edge beams<br>
Rt  seconds since the last move (rest timer) <br>
Pn  beam (1-15) the fly most recently entered <br>
Ct  legacy single-row format (only appears with status 51 = no data, i.e. while the monitor was being restarted between runs -> these minutes are treated as gaps) <br>

**What is computed** <br><br>

24-h windows are cut from the continuous record, tubes are mapped to labels, labels are parsed into Treatment / Dose / Strain / Sex. <br>
Sleep = >=5 min with zero moves (Pfeiffenberger et al. 2010, SLEEP_MIN to change). <br>
ZT is derived from the light sensor (ZT0 = median lights-on); DD windows are flagged. <br>
Per-fly metrics (activity, sleep by phase, bouts, latency, position), QC flags, stats (Mann-Whitney vs control per stratum, OLS/ANOVA pooled), and figures. <br>
