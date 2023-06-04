<h1><span style="font-family:Arial,Helvetica,sans-serif">Using a&nbsp;Wireshark&nbsp;TCP/HTTP log</span></h1>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Review the following scenario. Then complete the step-by-step instructions.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">You work as a security analyst for a travel agency that advertises sales and promotions on the company&rsquo;s website. The employees of the company regularly access the company&rsquo;s sales webpage to search for vacation packages their customers might like.&nbsp;</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company&rsquo;s website, but you receive a connection timeout error message in your browser.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company&rsquo;s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won&rsquo;t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.</span></span></p>

<p>&nbsp;</p>

<p><strong><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Review the Wireshark&nbsp;TCP/HTTP log</span></span></strong></p>

<p>&nbsp;</p>

<table border="1" cellpadding="1" cellspacing="1" style="width:750px">
	<thead>
		<tr>
			<td>No.</td>
			<td>Time</td>
			<td>Source</td>
			<td>Destination</td>
			<td>Protocol</td>
			<td>Info</td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>47</td>
			<td>3.144521</td>
			<td>198.51.100.23</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>42584-&gt;443 [SYN] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>48</td>
			<td>3.195755</td>
			<td>192.0.2.1</td>
			<td>198.51.100.23</td>
			<td>TCP</td>
			<td>443-&gt;42584 [SYN, ACK] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>49</td>
			<td>3.246989</td>
			<td>198.51.100.23</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>42584-&gt;443 [ACK] Seq=1 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>50</td>
			<td>3.298223</td>
			<td>198.51.100.23</td>
			<td>192.0.2.1</td>
			<td>HTTP</td>
			<td>GET /sales.html HTTP/1.1</td>
		</tr>
		<tr>
			<td>51</td>
			<td>3.349457</td>
			<td>192.0.2.1</td>
			<td>198.51.100.23</td>
			<td>HTTP</td>
			<td>HTTP/1.1 200 OK (text/html)</td>
		</tr>
		<tr>
			<td>52</td>
			<td>3.390692</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>53</td>
			<td>3.441926</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [SYN, ACK] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>54</td>
			<td>3.49316</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [ACK Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>55</td>
			<td>3.544394</td>
			<td>198.51.100.14</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>14785-&gt;443 [SYN] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>56</td>
			<td>3.599628</td>
			<td>192.0.2.1</td>
			<td>198.51.100.14</td>
			<td>TCP</td>
			<td>443-&gt;14785 [SYN, ACK] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>57</td>
			<td>3.664863</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>58</td>
			<td>3.730097</td>
			<td>198.51.100.14</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>14785-&gt;443 [ACK] Seq=1 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>59</td>
			<td>3.795332</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>60</td>
			<td>3.860567</td>
			<td>198.51.100.14</td>
			<td>192.0.2.1</td>
			<td>HTTP</td>
			<td>GET /sales.html HTTP/1.1</td>
		</tr>
		<tr>
			<td>61</td>
			<td>3.939499</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>62</td>
			<td>4.018431</td>
			<td>192.0.2.1</td>
			<td>198.51.100.14</td>
			<td>HTTP</td>
			<td>HTTP/1.1 200 OK (text/html)</td>
		</tr>
		<tr>
			<td>63</td>
			<td>4.097363</td>
			<td>198.51.100.5</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>33638-&gt;443 [SYN] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>64</td>
			<td>4.176295</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [SYN, ACK] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>65</td>
			<td>4.255227</td>
			<td>192.0.2.1</td>
			<td>198.51.100.5</td>
			<td>TCP</td>
			<td>443-&gt;33638 [SYN, ACK] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>66</td>
			<td>4.256159</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>67</td>
			<td>5.235091</td>
			<td>198.51.100.5</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>33638-&gt;443 [ACK] Seq=1 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>68</td>
			<td>5.236023</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>69</td>
			<td>5.236955</td>
			<td>198.51.100.16</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>32641-&gt;443 [SYN] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>70</td>
			<td>5.237887</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>71</td>
			<td>6.228728</td>
			<td>198.51.100.5</td>
			<td>192.0.2.1</td>
			<td>HTTP</td>
			<td>GET /sales.html HTTP/1.1</td>
		</tr>
		<tr>
			<td>72</td>
			<td>6.229638</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>73</td>
			<td>6.230548</td>
			<td>192.0.2.1</td>
			<td>198.51.100.16</td>
			<td>TCP</td>
			<td>443-&gt;32641 [RST, ACK] Seq=0 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>74</td>
			<td>6.330539</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>75</td>
			<td>6.330885</td>
			<td>198.51.100.7</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>42584-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>76</td>
			<td>6.331231</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>77</td>
			<td>7.330577</td>
			<td>192.0.2.1</td>
			<td>198.51.100.5</td>
			<td>TCP</td>
			<td>HTTP/1.1 504 Gateway Time-out (text/html)</td>
		</tr>
		<tr>
			<td>78</td>
			<td>7.351323</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>79</td>
			<td>7.360768</td>
			<td>198.51.100.22</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>6345-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>80</td>
			<td>7.380773</td>
			<td>192.0.2.1</td>
			<td>198.51.100.7</td>
			<td>TCP</td>
			<td>443-&gt;42584 [RST, ACK] Seq=1 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>81</td>
			<td>7.380878</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>82</td>
			<td>7.383879</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>83</td>
			<td>7.482754</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>84</td>
			<td>7.581629</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>85</td>
			<td>7.680504</td>
			<td>192.0.2.1</td>
			<td>198.51.100.22</td>
			<td>TCP</td>
			<td>443-&gt;6345 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>86</td>
			<td>7.709377</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>87</td>
			<td>7.738241</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>88</td>
			<td>7.767105</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>89</td>
			<td>13.895969</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>90</td>
			<td>13.919832</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>91</td>
			<td>13.943695</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>92</td>
			<td>13.967558</td>
			<td>192.0.2.1</td>
			<td>198.51.100.16</td>
			<td>TCP</td>
			<td>443-&gt;32641 [RST, ACK] Seq=1 Win-5792 Len=120...</td>
		</tr>
		<tr>
			<td>93</td>
			<td>13.991421</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>94</td>
			<td>14.015245</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>95</td>
			<td>14.439072</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>96</td>
			<td>14.862899</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>97</td>
			<td>14.886727</td>
			<td>198.51.100.9</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>4631-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>98</td>
			<td>15.310554</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>99</td>
			<td>15.734381</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>100</td>
			<td>16.158208</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>101</td>
			<td>16.582035</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>102</td>
			<td>17.005862</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>103</td>
			<td>17.429678</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>104</td>
			<td>17.452693</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>105</td>
			<td>17.475708</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>106</td>
			<td>17.498723</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>107</td>
			<td>17.521738</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>108</td>
			<td>17.544753</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>109</td>
			<td>17.567768</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>110</td>
			<td>17.590783</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>111</td>
			<td>18.413795</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>112</td>
			<td>18.436807</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>113</td>
			<td>18.459819</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>114</td>
			<td>18.482831</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>115</td>
			<td>18.506655</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>116</td>
			<td>18.529667</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>117</td>
			<td>18.552679</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>118</td>
			<td>18.875692</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>119</td>
			<td>19.198705</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>120</td>
			<td>19.521718</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>121</td>
			<td>19.844731</td>
			<td>192.0.2.1</td>
			<td>198.51.100.9</td>
			<td>TCP</td>
			<td>443-&gt;4631 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>122</td>
			<td>20.167744</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>123</td>
			<td>20.490757</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>124</td>
			<td>20.81377</td>
			<td>192.0.2.1</td>
			<td>203.0.113.0</td>
			<td>TCP</td>
			<td>443-&gt;54770 [RST, ACK] Seq=1 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>125</td>
			<td>21.136783</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>126</td>
			<td>21.459796</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>127</td>
			<td>21.782809</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>128</td>
			<td>22.105822</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>129</td>
			<td>22.428835</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>130</td>
			<td>22.751848</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>131</td>
			<td>23.074861</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>132</td>
			<td>23.397874</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>133</td>
			<td>23.720887</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>134</td>
			<td>24.0439</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>135</td>
			<td>24.366913</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>136</td>
			<td>24.689926</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>137</td>
			<td>25.012939</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>138</td>
			<td>25.335952</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>139</td>
			<td>25.658965</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>140</td>
			<td>25.981978</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>141</td>
			<td>26.304991</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>142</td>
			<td>26.628004</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>143</td>
			<td>26.951017</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>144</td>
			<td>27.27403</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>145</td>
			<td>27.597043</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>146</td>
			<td>27.920056</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>147</td>
			<td>28.243069</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>148</td>
			<td>28.566082</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>149</td>
			<td>28.889095</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>150</td>
			<td>29.212108</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>151</td>
			<td>29.535121</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>152</td>
			<td>29.858134</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>153</td>
			<td>30.181147</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>154</td>
			<td>30.50416</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>155</td>
			<td>30.827173</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>156</td>
			<td>31.150186</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>157</td>
			<td>31.473199</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>158</td>
			<td>31.796212</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>159</td>
			<td>32.119225</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>160</td>
			<td>32.442238</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>161</td>
			<td>32.765251</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>162</td>
			<td>33.088264</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>163</td>
			<td>33.411277</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>164</td>
			<td>33.73429</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>165</td>
			<td>34.057303</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>166</td>
			<td>34.380316</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>167</td>
			<td>34.703329</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>168</td>
			<td>35.026342</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>169</td>
			<td>35.349355</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>170</td>
			<td>35.672368</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>171</td>
			<td>35.995381</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>172</td>
			<td>36.318394</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>173</td>
			<td>36.641407</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>174</td>
			<td>36.96442</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>175</td>
			<td>37.287433</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>176</td>
			<td>37.610446</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>177</td>
			<td>37.933459</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>178</td>
			<td>38.256472</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>179</td>
			<td>38.579485</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>180</td>
			<td>38.902498</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>181</td>
			<td>39.225511</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>182</td>
			<td>39.548524</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>183</td>
			<td>39.871537</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>184</td>
			<td>40.19455</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>185</td>
			<td>40.517563</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>186</td>
			<td>40.840576</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>187</td>
			<td>41.163589</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>188</td>
			<td>41.486602</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>189</td>
			<td>41.809615</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>190</td>
			<td>42.132628</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>191</td>
			<td>42.455641</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>192</td>
			<td>42.778654</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>193</td>
			<td>43.101667</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>194</td>
			<td>43.42468</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>195</td>
			<td>43.747693</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>196</td>
			<td>44.070706</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>197</td>
			<td>44.393719</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>198</td>
			<td>44.716732</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>199</td>
			<td>45.039745</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>200</td>
			<td>45.362758</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>201</td>
			<td>45.685771</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>202</td>
			<td>46.008784</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>203</td>
			<td>46.331797</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>204</td>
			<td>46.65481</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>205</td>
			<td>46.977823</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>206</td>
			<td>47.300836</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>207</td>
			<td>47.623849</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>208</td>
			<td>47.946862</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>209</td>
			<td>48.269875</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>210</td>
			<td>48.592888</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>211</td>
			<td>48.915901</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>212</td>
			<td>49.238914</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>213</td>
			<td>49.561927</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>214</td>
			<td>49.88494</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>214</td>
			<td>50.207953</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>214</td>
			<td>50.530966</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>214</td>
			<td>50.853979</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>214</td>
			<td>51.176992</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>214</td>
			<td>51.500005</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
		<tr>
			<td>214</td>
			<td>51.823018</td>
			<td>203.0.113.0</td>
			<td>192.0.2.1</td>
			<td>TCP</td>
			<td>54770-&gt;443 [SYN] Seq=0 Win=5792 Len=0...</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<p><strong><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif"><span style="color:#000000">Section 1: Identify the type of attack that may have caused this&nbsp;network interruption</span></span></span></strong></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">One possible reason why the website shows an error message saying it can&#39;t connect could be attributed to a Denial-of-Service (DoS) attack. The examination of the logs reveals a pattern where the web server ceases to respond following an excessive influx of SYN packet requests. This pattern aligns with the type of DoS attack called SYN flooding.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Imagine the website as a busy store and the customers are the people trying to access it. In this case, there are some bad actors who are sending too many requests to the website all at once. It&#39;s like a huge crowd trying to enter the store at the same time, overwhelming the store and making it unable to serve anyone properly. This kind of attack is called a &quot;flooding&quot; attack, and it&#39;s like the bad actors are flooding the website with requests, causing it to stop working.</span></span></p>

<p><br />
<span style="font-size:12pt"><span style="font-family:Arial"><span style="color:#000000"><strong>Section 2: Explain how the attack is causing the website to malfunction</strong></span></span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">When visitors try to connect to a website, they go through a special process called a &quot;handshake&quot; using a protocol called TCP. This handshake has three steps:</span></span></p>

<ol>
	<li><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">First, the visitor sends a message (called a SYN packet) to the website, asking if it can connect.</span></span></li>
	<li><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">The website responds with a message (called a SYN-ACK packet), saying it accepts the connection request and sets aside resources to handle it.</span></span></li>
	<li><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Finally, the visitor sends another message (called an ACK packet) back to the website, confirming that it can connect.</span></span></li>
</ol>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">But sometimes, bad actors try to disrupt this process. In a SYN flood attack, they send a huge number of SYN packets all at once, overwhelming the website&#39;s resources. This means that when real visitors try to connect, there are no resources left for them, and the website can&#39;t process their requests.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">In the case of the website we&#39;re looking at, the logs show that it&#39;s been flooded with so many SYN packets that it can&#39;t handle them all. As a result, when people try to visit the website, they see a message saying the connection timed out because the server is too busy to handle their requests.</span></span></p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>&nbsp;</p>
