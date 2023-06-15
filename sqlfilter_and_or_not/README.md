<h1><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">SQL&nbsp;Filter with AND, OR, and NOT</span></span></h1>

<h3><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Question 1</span></span></h3>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Your team is investigating failed login attempts that were made after business hours. You want to retrieve this information from the login activity. You&rsquo;ll identify all unsuccessful attempts after 18:00.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The&nbsp;<code>login_time</code>&nbsp;column in the&nbsp;<code>log_in_attempts</code>&nbsp;table contains information on when login attempts were made. Office hours end at&nbsp;<code>18:00</code>.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The&nbsp;<code>success</code>&nbsp;column in the&nbsp;<code>log_in_attempts</code>&nbsp;table contains values of&nbsp;<code>TRUE</code>&nbsp;or&nbsp;<code>FALSE</code>&nbsp;to indicate whether the login was successful. MySQL stores Boolean values as&nbsp;<code>1</code>&nbsp;for&nbsp;<code>TRUE</code>, and&nbsp;<code>0</code>&nbsp;for&nbsp;<code>FALSE</code>. This means that&nbsp;<code>TRUE</code>&nbsp;is represented as&nbsp;<code>1</code>, and&nbsp;<code>FALSE</code>&nbsp;represented as&nbsp;<code>0</code>&nbsp;in the&nbsp;<code>success</code>&nbsp;column.</span></span></p>

<ul>
	<li><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Use the&nbsp;<code>AND</code>&nbsp;operator to retrieve the failed login attempts that occurred after business hours. Replace the&nbsp;<code>X</code>&nbsp;and&nbsp;<code>Y</code>&nbsp;with the correct values to filter for the records you need:</span></span></li>
</ul>

<h3><br />
<span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Results</span></span></h3>

<p><code>MariaDB [organization]&gt; Select *<br />
&nbsp; &nbsp; -&gt; From log_in_attempts<br />
&nbsp; &nbsp; -&gt; Where login_time &gt; &#39;18:00&#39; and success = &#39;0&#39;;<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
| event_id | username | login_date | login_time | country | ip_address &nbsp; &nbsp; &nbsp;| success |<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
| &nbsp; &nbsp; &nbsp; &nbsp;2 | apatel &nbsp; | 2022-05-10 | 20:27:27 &nbsp; | CAN &nbsp; &nbsp; | 192.168.205.12 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 18 | pwashing | 2022-05-11 | 19:28:50 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.66.142 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 20 | tshah &nbsp; &nbsp;| 2022-05-12 | 18:56:36 &nbsp; | MEXICO &nbsp;| 192.168.109.50 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 28 | aestrada | 2022-05-09 | 19:28:12 &nbsp; | MEXICO &nbsp;| 192.168.27.57 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 34 | drosas &nbsp; | 2022-05-11 | 21:02:04 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.45.93 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 42 | cgriffin | 2022-05-09 | 23:04:05 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.4.157 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 52 | cjackson | 2022-05-10 | 22:07:07 &nbsp; | CAN &nbsp; &nbsp; | 192.168.58.57 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 69 | wjaffrey | 2022-05-11 | 19:55:15 &nbsp; | USA &nbsp; &nbsp; | 192.168.100.17 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 82 | abernard | 2022-05-12 | 23:38:46 &nbsp; | MEX &nbsp; &nbsp; | 192.168.234.49 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 87 | apatel &nbsp; | 2022-05-08 | 22:38:31 &nbsp; | CANADA &nbsp;| 192.168.132.153 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 96 | ivelasco | 2022-05-09 | 22:36:36 &nbsp; | CAN &nbsp; &nbsp; | 192.168.84.194 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;104 | asundara | 2022-05-11 | 18:38:07 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.96.200 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;107 | bisles &nbsp; | 2022-05-12 | 20:25:57 &nbsp; | USA &nbsp; &nbsp; | 192.168.116.187 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;111 | aestrada | 2022-05-10 | 22:00:26 &nbsp; | MEXICO &nbsp;| 192.168.76.27 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;127 | abellmas | 2022-05-09 | 21:20:51 &nbsp; | CANADA &nbsp;| 192.168.70.122 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;131 | bisles &nbsp; | 2022-05-09 | 20:03:55 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.113.171 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;155 | cgriffin | 2022-05-12 | 22:18:42 &nbsp; | USA &nbsp; &nbsp; | 192.168.236.176 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;160 | jclark &nbsp; | 2022-05-10 | 20:49:00 &nbsp; | CANADA &nbsp;| 192.168.214.49 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;199 | yappiah &nbsp;| 2022-05-11 | 19:34:48 &nbsp; | MEXICO &nbsp;| 192.168.44.232 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
19 rows in set (0.160 sec)</code></p>

<p><strong><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:14px">How many failed login attempts occurred after 18:00?&nbsp; &nbsp;</span></span></strong><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:14px">19 is the correct answer</span></span></p>

<p>&nbsp;</p>

<h3><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:14px">Question 2</span></span></h3>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Your team is investigating a suspicious event that occurred on&nbsp;<code>2022-05-09</code>. You want to retrieve all login attempts that occurred on this day and the day before (<code>2022-05-08</code>).</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The&nbsp;<code>login_date</code>&nbsp;column in the&nbsp;<code>log_in_attempts</code>&nbsp;table contains information on the dates when login attempts were made.</span></span></p>

<ul>
	<li><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Use the&nbsp;<code>OR</code>&nbsp;operator to retrieve the failed login attempts on the specified days. Replace the&nbsp;<code>X</code>&nbsp;and&nbsp;<code>Y</code>&nbsp;with the correct values to filter for the records you need:</span></span></li>
</ul>

<h3><span style="font-family:Arial,Helvetica,sans-serif">Results</span></h3>

<p><span style="font-family:Arial,Helvetica,sans-serif"><code>MariaDB [organization]&gt; Select *<br />
&nbsp; &nbsp; -&gt; From log_in_attempts<br />
&nbsp; &nbsp; -&gt; Where login_date = &#39;2022-05-09&#39; OR login_date = &#39;2022-05-08&#39;;<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
| event_id | username | login_date | login_time | country | ip_address &nbsp; &nbsp; &nbsp;| success |<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
| &nbsp; &nbsp; &nbsp; &nbsp;1 | jrafael &nbsp;| 2022-05-09 | 04:56:27 &nbsp; | CAN &nbsp; &nbsp; | 192.168.243.140 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;3 | dkot &nbsp; &nbsp; | 2022-05-09 | 06:47:41 &nbsp; | USA &nbsp; &nbsp; | 192.168.151.162 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;4 | dkot &nbsp; &nbsp; | 2022-05-08 | 02:00:39 &nbsp; | USA &nbsp; &nbsp; | 192.168.178.71 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;8 | bisles &nbsp; | 2022-05-08 | 01:30:17 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.119.173 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 12 | dkot &nbsp; &nbsp; | 2022-05-08 | 09:11:34 &nbsp; | USA &nbsp; &nbsp; | 192.168.100.158 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 15 | lyamamot | 2022-05-09 | 17:17:26 &nbsp; | USA &nbsp; &nbsp; | 192.168.183.51 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 24 | arusso &nbsp; | 2022-05-09 | 06:49:39 &nbsp; | MEXICO &nbsp;| 192.168.171.192 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 25 | sbaelish | 2022-05-09 | 07:04:02 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.33.137 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 26 | apatel &nbsp; | 2022-05-08 | 17:27:00 &nbsp; | CANADA &nbsp;| 192.168.123.105 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 28 | aestrada | 2022-05-09 | 19:28:12 &nbsp; | MEXICO &nbsp;| 192.168.27.57 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 30 | yappiah &nbsp;| 2022-05-09 | 03:22:22 &nbsp; | MEX &nbsp; &nbsp; | 192.168.124.48 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 32 | acook &nbsp; &nbsp;| 2022-05-09 | 02:52:02 &nbsp; | CANADA &nbsp;| 192.168.142.239 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 36 | asundara | 2022-05-08 | 09:00:42 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.78.151 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 38 | sbaelish | 2022-05-09 | 14:40:01 &nbsp; | USA &nbsp; &nbsp; | 192.168.60.42 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 39 | yappiah &nbsp;| 2022-05-09 | 07:56:40 &nbsp; | MEXICO &nbsp;| 192.168.57.115 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 42 | cgriffin | 2022-05-09 | 23:04:05 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.4.157 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 43 | mcouliba | 2022-05-08 | 02:35:34 &nbsp; | CANADA &nbsp;| 192.168.16.208 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 44 | daquino &nbsp;| 2022-05-08 | 07:02:35 &nbsp; | CANADA &nbsp;| 192.168.168.144 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 47 | dkot &nbsp; &nbsp; | 2022-05-08 | 05:06:45 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.233.24 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 49 | asundara | 2022-05-08 | 14:00:01 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.173.213 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 53 | nmason &nbsp; | 2022-05-08 | 11:51:38 &nbsp; | CAN &nbsp; &nbsp; | 192.168.133.188 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 56 | acook &nbsp; &nbsp;| 2022-05-08 | 04:56:30 &nbsp; | CAN &nbsp; &nbsp; | 192.168.209.130 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 58 | ivelasco | 2022-05-09 | 17:20:54 &nbsp; | CAN &nbsp; &nbsp; | 192.168.57.162 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 61 | dtanaka &nbsp;| 2022-05-09 | 09:45:18 &nbsp; | USA &nbsp; &nbsp; | 192.168.98.221 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 65 | aalonso &nbsp;| 2022-05-09 | 23:42:12 &nbsp; | MEX &nbsp; &nbsp; | 192.168.52.37 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 66 | aestrada | 2022-05-08 | 21:58:32 &nbsp; | MEX &nbsp; &nbsp; | 192.168.67.223 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 67 | abernard | 2022-05-09 | 11:53:41 &nbsp; | MEX &nbsp; &nbsp; | 192.168.118.29 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 68 | mrah &nbsp; &nbsp; | 2022-05-08 | 17:16:13 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.42.248 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 70 | tmitchel | 2022-05-09 | 10:55:17 &nbsp; | MEXICO &nbsp;| 192.168.87.199 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 71 | mcouliba | 2022-05-09 | 06:57:42 &nbsp; | CAN &nbsp; &nbsp; | 192.168.55.169 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 72 | alevitsk | 2022-05-08 | 12:09:10 &nbsp; | CANADA &nbsp;| 192.168.139.176 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 79 | abernard | 2022-05-09 | 11:41:15 &nbsp; | MEX &nbsp; &nbsp; | 192.168.158.170 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 80 | cjackson | 2022-05-08 | 02:18:10 &nbsp; | CANADA &nbsp;| 192.168.33.140 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 83 | lrodriqu | 2022-05-08 | 08:10:23 &nbsp; | USA &nbsp; &nbsp; | 192.168.67.69 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 87 | apatel &nbsp; | 2022-05-08 | 22:38:31 &nbsp; | CANADA &nbsp;| 192.168.132.153 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 90 | gesparza | 2022-05-09 | 00:49:05 &nbsp; | CANADA &nbsp;| 192.168.87.201 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 92 | pwashing | 2022-05-08 | 00:36:12 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.247.219 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 96 | ivelasco | 2022-05-09 | 22:36:36 &nbsp; | CAN &nbsp; &nbsp; | 192.168.84.194 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 97 | jreckley | 2022-05-09 | 02:49:23 &nbsp; | MEXICO &nbsp;| 192.168.32.231 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;101 | sbaelish | 2022-05-08 | 12:01:22 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.145.158 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;102 | jreckley | 2022-05-09 | 16:51:44 &nbsp; | MEX &nbsp; &nbsp; | 192.168.108.13 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;108 | daquino &nbsp;| 2022-05-09 | 21:30:48 &nbsp; | CANADA &nbsp;| 192.168.15.110 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;110 | mabadi &nbsp; | 2022-05-09 | 00:01:54 &nbsp; | USA &nbsp; &nbsp; | 192.168.90.124 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;112 | rjensen &nbsp;| 2022-05-09 | 09:22:05 &nbsp; | MEX &nbsp; &nbsp; | 192.168.69.116 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;117 | bsand &nbsp; &nbsp;| 2022-05-08 | 00:19:11 &nbsp; | USA &nbsp; &nbsp; | 192.168.197.187 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;120 | tmitchel | 2022-05-09 | 02:58:17 &nbsp; | MEXICO &nbsp;| 192.168.134.62 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;127 | abellmas | 2022-05-09 | 21:20:51 &nbsp; | CANADA &nbsp;| 192.168.70.122 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;128 | jclark &nbsp; | 2022-05-09 | 10:45:59 &nbsp; | CANADA &nbsp;| 192.168.122.169 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;131 | bisles &nbsp; | 2022-05-09 | 20:03:55 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.113.171 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;134 | iuduike &nbsp;| 2022-05-09 | 06:46:40 &nbsp; | USA &nbsp; &nbsp; | 192.168.22.115 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;135 | bsand &nbsp; &nbsp;| 2022-05-09 | 14:06:33 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.91.238 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;144 | daquino &nbsp;| 2022-05-09 | 11:09:32 &nbsp; | CANADA &nbsp;| 192.168.139.9 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;145 | ivelasco | 2022-05-08 | 09:06:02 &nbsp; | CANADA &nbsp;| 192.168.39.196 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;147 | yappiah &nbsp;| 2022-05-08 | 06:04:34 &nbsp; | MEX &nbsp; &nbsp; | 192.168.65.245 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;148 | daquino &nbsp;| 2022-05-08 | 06:15:55 &nbsp; | CANADA &nbsp;| 192.168.135.6 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;150 | nmason &nbsp; | 2022-05-08 | 14:40:02 &nbsp; | CAN &nbsp; &nbsp; | 192.168.204.124 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;151 | mabadi &nbsp; | 2022-05-09 | 16:29:46 &nbsp; | USA &nbsp; &nbsp; | 192.168.30.225 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;158 | smartell | 2022-05-09 | 19:30:32 &nbsp; | MEXICO &nbsp;| 192.168.190.178 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;161 | abellmas | 2022-05-09 | 13:25:50 &nbsp; | CAN &nbsp; &nbsp; | 192.168.180.205 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;162 | yappiah &nbsp;| 2022-05-09 | 04:51:22 &nbsp; | MEXICO &nbsp;| 192.168.162.100 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;163 | tmitchel | 2022-05-08 | 09:21:16 &nbsp; | MEX &nbsp; &nbsp; | 192.168.119.29 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;165 | jreckley | 2022-05-08 | 15:28:43 &nbsp; | MEXICO &nbsp;| 192.168.34.193 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;168 | jlansky &nbsp;| 2022-05-08 | 13:25:42 &nbsp; | USA &nbsp; &nbsp; | 192.168.210.94 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;169 | alevitsk | 2022-05-08 | 08:10:43 &nbsp; | CANADA &nbsp;| 192.168.210.228 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;170 | sbaelish | 2022-05-09 | 16:43:18 &nbsp; | USA &nbsp; &nbsp; | 192.168.65.113 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;172 | mabadi &nbsp; | 2022-05-08 | 08:06:50 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.180.41 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;178 | sgilmore | 2022-05-08 | 12:27:22 &nbsp; | CAN &nbsp; &nbsp; | 192.168.52.216 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;184 | alevitsk | 2022-05-08 | 03:09:48 &nbsp; | CAN &nbsp; &nbsp; | 192.168.33.70 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;186 | bisles &nbsp; | 2022-05-09 | 04:29:17 &nbsp; | USA &nbsp; &nbsp; | 192.168.40.72 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;187 | arusso &nbsp; | 2022-05-09 | 00:36:26 &nbsp; | MEX &nbsp; &nbsp; | 192.168.77.137 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;189 | nmason &nbsp; | 2022-05-08 | 05:37:24 &nbsp; | CANADA &nbsp;| 192.168.168.117 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;190 | jsoto &nbsp; &nbsp;| 2022-05-09 | 05:09:21 &nbsp; | USA &nbsp; &nbsp; | 192.168.25.60 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;191 | cjackson | 2022-05-08 | 06:46:07 &nbsp; | CANADA &nbsp;| 192.168.7.187 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;193 | lrodriqu | 2022-05-08 | 07:11:29 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.125.240 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;197 | jsoto &nbsp; &nbsp;| 2022-05-08 | 09:05:09 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.36.21 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
75 rows in set (0.001 sec)</code></span></p>

<p><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">How many login attempts were made on these two days? </span></span></strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">75 is the correct answer</span></span></p>

<h3><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Question 3</span></span></h3>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Now, your team is investigating logins that did not originate in Mexico, and you need to find this information. Note that the country field includes entries with&nbsp;<code>MEX</code>&nbsp;and&nbsp;<code>MEXICO</code>. You should use the&nbsp;<code>NOT</code>&nbsp;and&nbsp;<code>LIKE</code>&nbsp;operators and the matching pattern&nbsp;<code>MEX%</code>.</span></span></p>

<ul>
	<li><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Run the following SQL query to retrieve login attempts that did not originate in Mexico. Replace&nbsp;<code>X</code>&nbsp;with the correct operator and&nbsp;<code>Y</code>&nbsp;with the correct pattern to filter for the information you need:</span></span></li>
</ul>

<h3><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Results</span></span></h3>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><code>MariaDB [organization]&gt; Select *&nbsp;<br />
&nbsp; &nbsp; -&gt; From log_in_attempts<br />
&nbsp; &nbsp; -&gt; Where NOT country LIKE &#39;MEX%&#39;;<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
| event_id | username | login_date | login_time | country | ip_address &nbsp; &nbsp; &nbsp;| success |<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
| &nbsp; &nbsp; &nbsp; &nbsp;1 | jrafael &nbsp;| 2022-05-09 | 04:56:27 &nbsp; | CAN &nbsp; &nbsp; | 192.168.243.140 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;2 | apatel &nbsp; | 2022-05-10 | 20:27:27 &nbsp; | CAN &nbsp; &nbsp; | 192.168.205.12 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;3 | dkot &nbsp; &nbsp; | 2022-05-09 | 06:47:41 &nbsp; | USA &nbsp; &nbsp; | 192.168.151.162 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;4 | dkot &nbsp; &nbsp; | 2022-05-08 | 02:00:39 &nbsp; | USA &nbsp; &nbsp; | 192.168.178.71 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;5 | jrafael &nbsp;| 2022-05-11 | 03:05:59 &nbsp; | CANADA &nbsp;| 192.168.86.232 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;7 | eraab &nbsp; &nbsp;| 2022-05-11 | 01:45:14 &nbsp; | CAN &nbsp; &nbsp; | 192.168.170.243 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; &nbsp;8 | bisles &nbsp; | 2022-05-08 | 01:30:17 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.119.173 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 10 | jrafael &nbsp;| 2022-05-12 | 09:33:19 &nbsp; | CANADA &nbsp;| 192.168.228.221 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 11 | sgilmore | 2022-05-11 | 10:16:29 &nbsp; | CANADA &nbsp;| 192.168.140.81 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 12 | dkot &nbsp; &nbsp; | 2022-05-08 | 09:11:34 &nbsp; | USA &nbsp; &nbsp; | 192.168.100.158 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 13 | mrah &nbsp; &nbsp; | 2022-05-11 | 09:29:34 &nbsp; | USA &nbsp; &nbsp; | 192.168.246.135 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 14 | sbaelish | 2022-05-10 | 10:20:18 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.16.99 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 15 | lyamamot | 2022-05-09 | 17:17:26 &nbsp; | USA &nbsp; &nbsp; | 192.168.183.51 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 16 | mcouliba | 2022-05-11 | 06:44:22 &nbsp; | CAN &nbsp; &nbsp; | 192.168.172.189 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 17 | pwashing | 2022-05-11 | 02:33:02 &nbsp; | USA &nbsp; &nbsp; | 192.168.81.89 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 18 | pwashing | 2022-05-11 | 19:28:50 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.66.142 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 19 | jhill &nbsp; &nbsp;| 2022-05-12 | 13:09:04 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.142.245 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 21 | iuduike &nbsp;| 2022-05-11 | 17:50:00 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.131.147 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 25 | sbaelish | 2022-05-09 | 07:04:02 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.33.137 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 26 | apatel &nbsp; | 2022-05-08 | 17:27:00 &nbsp; | CANADA &nbsp;| 192.168.123.105 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 29 | bisles &nbsp; | 2022-05-11 | 01:21:22 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.85.186 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 31 | acook &nbsp; &nbsp;| 2022-05-12 | 17:36:45 &nbsp; | CANADA &nbsp;| 192.168.58.232 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 32 | acook &nbsp; &nbsp;| 2022-05-09 | 02:52:02 &nbsp; | CANADA &nbsp;| 192.168.142.239 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 33 | zbernal &nbsp;| 2022-05-11 | 02:52:10 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.72.59 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 34 | drosas &nbsp; | 2022-05-11 | 21:02:04 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.45.93 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 36 | asundara | 2022-05-08 | 09:00:42 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.78.151 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 37 | eraab &nbsp; &nbsp;| 2022-05-10 | 06:03:41 &nbsp; | CANADA &nbsp;| 192.168.152.148 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 38 | sbaelish | 2022-05-09 | 14:40:01 &nbsp; | USA &nbsp; &nbsp; | 192.168.60.42 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 41 | apatel &nbsp; | 2022-05-10 | 17:39:42 &nbsp; | CANADA &nbsp;| 192.168.46.207 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 42 | cgriffin | 2022-05-09 | 23:04:05 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.4.157 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 43 | mcouliba | 2022-05-08 | 02:35:34 &nbsp; | CANADA &nbsp;| 192.168.16.208 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 44 | daquino &nbsp;| 2022-05-08 | 07:02:35 &nbsp; | CANADA &nbsp;| 192.168.168.144 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 45 | dtanaka &nbsp;| 2022-05-11 | 10:28:54 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.223.157 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 46 | eraab &nbsp; &nbsp;| 2022-05-11 | 11:29:27 &nbsp; | CAN &nbsp; &nbsp; | 192.168.24.12 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 47 | dkot &nbsp; &nbsp; | 2022-05-08 | 05:06:45 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.233.24 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 48 | asundara | 2022-05-11 | 03:18:45 &nbsp; | USA &nbsp; &nbsp; | 192.168.72.10 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 49 | asundara | 2022-05-08 | 14:00:01 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.173.213 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 50 | jclark &nbsp; | 2022-05-10 | 10:48:02 &nbsp; | CANADA &nbsp;| 192.168.174.117 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 51 | jrafael &nbsp;| 2022-05-10 | 22:40:01 &nbsp; | CANADA &nbsp;| 192.168.148.115 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 52 | cjackson | 2022-05-10 | 22:07:07 &nbsp; | CAN &nbsp; &nbsp; | 192.168.58.57 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 53 | nmason &nbsp; | 2022-05-08 | 11:51:38 &nbsp; | CAN &nbsp; &nbsp; | 192.168.133.188 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 55 | jlansky &nbsp;| 2022-05-11 | 05:15:34 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.6.170 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 56 | acook &nbsp; &nbsp;| 2022-05-08 | 04:56:30 &nbsp; | CAN &nbsp; &nbsp; | 192.168.209.130 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 57 | asundara | 2022-05-12 | 21:13:02 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.211.201 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 58 | ivelasco | 2022-05-09 | 17:20:54 &nbsp; | CAN &nbsp; &nbsp; | 192.168.57.162 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 60 | acook &nbsp; &nbsp;| 2022-05-11 | 21:46:00 &nbsp; | CAN &nbsp; &nbsp; | 192.168.54.45 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 61 | dtanaka &nbsp;| 2022-05-09 | 09:45:18 &nbsp; | USA &nbsp; &nbsp; | 192.168.98.221 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 64 | apatel &nbsp; | 2022-05-10 | 22:00:09 &nbsp; | CANADA &nbsp;| 192.168.172.71 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 68 | mrah &nbsp; &nbsp; | 2022-05-08 | 17:16:13 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.42.248 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 69 | wjaffrey | 2022-05-11 | 19:55:15 &nbsp; | USA &nbsp; &nbsp; | 192.168.100.17 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 71 | mcouliba | 2022-05-09 | 06:57:42 &nbsp; | CAN &nbsp; &nbsp; | 192.168.55.169 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 72 | alevitsk | 2022-05-08 | 12:09:10 &nbsp; | CANADA &nbsp;| 192.168.139.176 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 73 | zbernal &nbsp;| 2022-05-10 | 17:46:45 &nbsp; | USA &nbsp; &nbsp; | 192.168.80.46 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 74 | nmason &nbsp; | 2022-05-11 | 15:55:48 &nbsp; | CAN &nbsp; &nbsp; | 192.168.162.2 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 75 | zbernal &nbsp;| 2022-05-12 | 04:14:35 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.188.63 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 76 | bmoreno &nbsp;| 2022-05-10 | 10:53:55 &nbsp; | CAN &nbsp; &nbsp; | 192.168.61.200 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 77 | wjaffrey | 2022-05-12 | 08:37:59 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.106.183 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 80 | cjackson | 2022-05-08 | 02:18:10 &nbsp; | CANADA &nbsp;| 192.168.33.140 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 83 | lrodriqu | 2022-05-08 | 08:10:23 &nbsp; | USA &nbsp; &nbsp; | 192.168.67.69 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 84 | jrafael &nbsp;| 2022-05-11 | 09:26:17 &nbsp; | CAN &nbsp; &nbsp; | 192.168.243.203 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 86 | dtanaka &nbsp;| 2022-05-10 | 10:22:20 &nbsp; | USA &nbsp; &nbsp; | 192.168.197.135 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 87 | apatel &nbsp; | 2022-05-08 | 22:38:31 &nbsp; | CANADA &nbsp;| 192.168.132.153 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 89 | dkot &nbsp; &nbsp; | 2022-05-12 | 10:52:00 &nbsp; | USA &nbsp; &nbsp; | 192.168.128.75 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 90 | gesparza | 2022-05-09 | 00:49:05 &nbsp; | CANADA &nbsp;| 192.168.87.201 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 91 | jhill &nbsp; &nbsp;| 2022-05-11 | 17:46:47 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.172.74 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp; 92 | pwashing | 2022-05-08 | 00:36:12 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.247.219 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 96 | ivelasco | 2022-05-09 | 22:36:36 &nbsp; | CAN &nbsp; &nbsp; | 192.168.84.194 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 98 | gesparza | 2022-05-11 | 06:30:14 &nbsp; | CANADA &nbsp;| 192.168.148.80 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp; 99 | mcouliba | 2022-05-12 | 11:54:14 &nbsp; | CANADA &nbsp;| 192.168.218.160 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;101 | sbaelish | 2022-05-08 | 12:01:22 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.145.158 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;103 | jhill &nbsp; &nbsp;| 2022-05-11 | 09:10:54 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.60.153 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;104 | asundara | 2022-05-11 | 18:38:07 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.96.200 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;105 | cjackson | 2022-05-12 | 19:36:42 &nbsp; | CAN &nbsp; &nbsp; | 192.168.247.153 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;107 | bisles &nbsp; | 2022-05-12 | 20:25:57 &nbsp; | USA &nbsp; &nbsp; | 192.168.116.187 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;108 | daquino &nbsp;| 2022-05-09 | 21:30:48 &nbsp; | CANADA &nbsp;| 192.168.15.110 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;109 | mcouliba | 2022-05-10 | 04:43:15 &nbsp; | CANADA &nbsp;| 192.168.39.246 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;110 | mabadi &nbsp; | 2022-05-09 | 00:01:54 &nbsp; | USA &nbsp; &nbsp; | 192.168.90.124 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;113 | gesparza | 2022-05-10 | 00:40:00 &nbsp; | CAN &nbsp; &nbsp; | 192.168.64.133 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;115 | ivelasco | 2022-05-10 | 23:06:01 &nbsp; | CAN &nbsp; &nbsp; | 192.168.154.1 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;117 | bsand &nbsp; &nbsp;| 2022-05-08 | 00:19:11 &nbsp; | USA &nbsp; &nbsp; | 192.168.197.187 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;121 | btang &nbsp; &nbsp;| 2022-05-10 | 22:00:36 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.80.143 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;123 | bmoreno &nbsp;| 2022-05-10 | 04:43:30 &nbsp; | CANADA &nbsp;| 192.168.98.2 &nbsp; &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;124 | asundara | 2022-05-12 | 10:51:21 &nbsp; | USA &nbsp; &nbsp; | 192.168.136.29 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;125 | bisles &nbsp; | 2022-05-11 | 08:36:19 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.74.9 &nbsp; &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;126 | jrafael &nbsp;| 2022-05-12 | 18:47:52 &nbsp; | CAN &nbsp; &nbsp; | 192.168.22.16 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;127 | abellmas | 2022-05-09 | 21:20:51 &nbsp; | CANADA &nbsp;| 192.168.70.122 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;128 | jclark &nbsp; | 2022-05-09 | 10:45:59 &nbsp; | CANADA &nbsp;| 192.168.122.169 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;129 | drosas &nbsp; | 2022-05-12 | 15:39:40 &nbsp; | USA &nbsp; &nbsp; | 192.168.152.200 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;130 | mrah &nbsp; &nbsp; | 2022-05-11 | 02:54:21 &nbsp; | USA &nbsp; &nbsp; | 192.168.102.147 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;131 | bisles &nbsp; | 2022-05-09 | 20:03:55 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.113.171 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;133 | asundara | 2022-05-12 | 05:57:04 &nbsp; | USA &nbsp; &nbsp; | 192.168.6.9 &nbsp; &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;134 | iuduike &nbsp;| 2022-05-09 | 06:46:40 &nbsp; | USA &nbsp; &nbsp; | 192.168.22.115 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;135 | bsand &nbsp; &nbsp;| 2022-05-09 | 14:06:33 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.91.238 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;136 | mabadi &nbsp; | 2022-05-10 | 06:56:44 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.214.234 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;137 | jrafael &nbsp;| 2022-05-12 | 02:42:37 &nbsp; | CAN &nbsp; &nbsp; | 192.168.186.176 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;139 | apatel &nbsp; | 2022-05-11 | 01:54:36 &nbsp; | CAN &nbsp; &nbsp; | 192.168.95.222 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;140 | btang &nbsp; &nbsp;| 2022-05-10 | 13:17:29 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.249.111 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;141 | btang &nbsp; &nbsp;| 2022-05-12 | 10:12:03 &nbsp; | USA &nbsp; &nbsp; | 192.168.82.139 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;142 | gesparza | 2022-05-11 | 06:31:14 &nbsp; | CANADA &nbsp;| 192.168.117.56 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;143 | jhill &nbsp; &nbsp;| 2022-05-11 | 00:30:22 &nbsp; | USA &nbsp; &nbsp; | 192.168.189.19 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;144 | daquino &nbsp;| 2022-05-09 | 11:09:32 &nbsp; | CANADA &nbsp;| 192.168.139.9 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;145 | ivelasco | 2022-05-08 | 09:06:02 &nbsp; | CANADA &nbsp;| 192.168.39.196 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;146 | nmason &nbsp; | 2022-05-10 | 02:25:55 &nbsp; | CANADA &nbsp;| 192.168.37.147 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;148 | daquino &nbsp;| 2022-05-08 | 06:15:55 &nbsp; | CANADA &nbsp;| 192.168.135.6 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;149 | jlansky &nbsp;| 2022-05-11 | 01:07:11 &nbsp; | USA &nbsp; &nbsp; | 192.168.238.42 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;150 | nmason &nbsp; | 2022-05-08 | 14:40:02 &nbsp; | CAN &nbsp; &nbsp; | 192.168.204.124 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;151 | mabadi &nbsp; | 2022-05-09 | 16:29:46 &nbsp; | USA &nbsp; &nbsp; | 192.168.30.225 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;152 | mabadi &nbsp; | 2022-05-12 | 10:24:43 &nbsp; | USA &nbsp; &nbsp; | 192.168.96.244 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;154 | jlansky &nbsp;| 2022-05-12 | 10:57:35 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.23.63 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;155 | cgriffin | 2022-05-12 | 22:18:42 &nbsp; | USA &nbsp; &nbsp; | 192.168.236.176 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;156 | btang &nbsp; &nbsp;| 2022-05-11 | 17:08:51 &nbsp; | USA &nbsp; &nbsp; | 192.168.243.95 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;159 | iuduike &nbsp;| 2022-05-12 | 16:59:50 &nbsp; | USA &nbsp; &nbsp; | 192.168.220.115 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;160 | jclark &nbsp; | 2022-05-10 | 20:49:00 &nbsp; | CANADA &nbsp;| 192.168.214.49 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;161 | abellmas | 2022-05-09 | 13:25:50 &nbsp; | CAN &nbsp; &nbsp; | 192.168.180.205 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;164 | jclark &nbsp; | 2022-05-12 | 21:15:52 &nbsp; | CAN &nbsp; &nbsp; | 192.168.18.34 &nbsp; | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;167 | jclark &nbsp; | 2022-05-12 | 15:47:45 &nbsp; | CAN &nbsp; &nbsp; | 192.168.146.51 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;168 | jlansky &nbsp;| 2022-05-08 | 13:25:42 &nbsp; | USA &nbsp; &nbsp; | 192.168.210.94 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;169 | alevitsk | 2022-05-08 | 08:10:43 &nbsp; | CANADA &nbsp;| 192.168.210.228 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;170 | sbaelish | 2022-05-09 | 16:43:18 &nbsp; | USA &nbsp; &nbsp; | 192.168.65.113 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;171 | drosas &nbsp; | 2022-05-10 | 16:32:55 &nbsp; | USA &nbsp; &nbsp; | 192.168.92.218 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;172 | mabadi &nbsp; | 2022-05-08 | 08:06:50 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.180.41 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;173 | asundara | 2022-05-12 | 23:17:52 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.58.217 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;174 | lyamamot | 2022-05-10 | 12:26:27 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.228.122 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;175 | jhill &nbsp; &nbsp;| 2022-05-10 | 00:17:09 &nbsp; | USA &nbsp; &nbsp; | 192.168.130.218 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;177 | wjaffrey | 2022-05-11 | 00:15:55 &nbsp; | USA &nbsp; &nbsp; | 192.168.144.165 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;178 | sgilmore | 2022-05-08 | 12:27:22 &nbsp; | CAN &nbsp; &nbsp; | 192.168.52.216 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;179 | jclark &nbsp; | 2022-05-12 | 04:08:17 &nbsp; | CAN &nbsp; &nbsp; | 192.168.232.93 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;181 | abellmas | 2022-05-10 | 13:37:05 &nbsp; | CAN &nbsp; &nbsp; | 192.168.60.111 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;182 | lyamamot | 2022-05-10 | 06:01:31 &nbsp; | USA &nbsp; &nbsp; | 192.168.106.52 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;183 | nmason &nbsp; | 2022-05-11 | 05:29:36 &nbsp; | CANADA &nbsp;| 192.168.137.147 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;184 | alevitsk | 2022-05-08 | 03:09:48 &nbsp; | CAN &nbsp; &nbsp; | 192.168.33.70 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;185 | jsoto &nbsp; &nbsp;| 2022-05-10 | 13:34:58 &nbsp; | USA &nbsp; &nbsp; | 192.168.151.91 &nbsp;| &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;186 | bisles &nbsp; | 2022-05-09 | 04:29:17 &nbsp; | USA &nbsp; &nbsp; | 192.168.40.72 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;188 | jsoto &nbsp; &nbsp;| 2022-05-11 | 00:39:09 &nbsp; | USA &nbsp; &nbsp; | 192.168.21.88 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;189 | nmason &nbsp; | 2022-05-08 | 05:37:24 &nbsp; | CANADA &nbsp;| 192.168.168.117 | &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;190 | jsoto &nbsp; &nbsp;| 2022-05-09 | 05:09:21 &nbsp; | USA &nbsp; &nbsp; | 192.168.25.60 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;191 | cjackson | 2022-05-08 | 06:46:07 &nbsp; | CANADA &nbsp;| 192.168.7.187 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;192 | bisles &nbsp; | 2022-05-10 | 08:32:03 &nbsp; | USA &nbsp; &nbsp; | 192.168.201.40 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;193 | lrodriqu | 2022-05-08 | 07:11:29 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.125.240 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;194 | jclark &nbsp; | 2022-05-12 | 14:11:04 &nbsp; | CAN &nbsp; &nbsp; | 192.168.197.247 | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;195 | alevitsk | 2022-05-11 | 06:59:13 &nbsp; | CANADA &nbsp;| 192.168.236.78 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
| &nbsp; &nbsp; &nbsp;196 | acook &nbsp; &nbsp;| 2022-05-10 | 09:56:48 &nbsp; | CAN &nbsp; &nbsp; | 192.168.52.90 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;197 | jsoto &nbsp; &nbsp;| 2022-05-08 | 09:05:09 &nbsp; | US &nbsp; &nbsp; &nbsp;| 192.168.36.21 &nbsp; | &nbsp; &nbsp; &nbsp; 0 |<br />
| &nbsp; &nbsp; &nbsp;200 | jclark &nbsp; | 2022-05-12 | 01:11:45 &nbsp; | CANADA &nbsp;| 192.168.91.103 &nbsp;| &nbsp; &nbsp; &nbsp; 1 |<br />
+----------+----------+------------+------------+---------+-----------------+---------+<br />
144 rows in set (0.018 sec)</code></span></span></p>

<p><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">How many login attempts were made outside of Mexico? </span></span></strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">144 attempts is the correct answer.</span></span></p>
