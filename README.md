# Test case prioritization based on fault sensitivity analysis using ranked NSGA-2
<p>In this project, a ranking-based NSGA-2 algorithm is employed for test case ordering and prioritization. The primary focus is on identifying and prioritizing test cases with sensitivity to faults, particularly those introduced by modifications or the addition of new software functionality. The approach utilizes historical data to inform the prioritization process.</p>

<p>A key component of the project is the incorporation of a Sensitive Index, which aids in identifying test cases that are particularly sensitive to faults. In addition to the Sensitive Index, the project emphasizes two other critical objectives in test prioritization: Execution Cost and APFD (Average Percentage of Faults Detected). These objectives collectively contribute to a comprehensive prioritization strategy for efficient and effective fault detection.</p>

<p>The Sensitive Index plays a pivotal role in highlighting test cases with a higher likelihood of revealing faults, especially those arising from recent modifications or the introduction of new software functionalities. Derived from historical data, the Sensitive Index allows the algorithm to assign higher priority to test cases that have demonstrated greater fault-revealing potential in the past.</p>

<p>Execution Cost, another objective in the prioritization process, considers the resource requirements associated with executing each test case. Balancing thorough testing with resource constraints is crucial for an efficient testing process.</p>


<p>To illustrate and validate the proposed methodology and the formulation of fitness functions, the project employs a small-scale case study named "Project P." This case study is designed to provide a practical demonstration of the methodology in action. Project P is depicted in Figure 2, providing an overview of its structure. The project comprises five modules and seven classes, and a dependency graph is presented to illustrate the relationships among these modules and classes.</p>


![image](https://github.com/CodeReformer/MOTCP/assets/156921147/443e69dd-4865-4288-80d7-82de9d49dbf5)
<br><i>(Description of small-scale project C: class; M: module; T: testcases; (a) Module dependency (b) Class Dependency)</i>

<table border="1">
  <caption>Table 1: Testcases v/s Fault matrix</caption>
  <tr>
    <th></th>
    <th>F0</th>
    <th>F1</th>
    <th>F2</th>
    <th>F3</th>
    <th>F4</th>
    <th>F5</th>
    <th>F6</th>
    <th>F7</th>
    <th>F8</th>
    <th>F9</th>
    <th>F10</th>
    <th>F11</th>
    <th>F12</th>
    <th>F13</th>
  </tr>
  <tr>
    <td>T0</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>T1</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>T2</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>T3</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>T4</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>T5</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
  </tr>
  <tr>
    <td>T6</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
  </tr>
  <tr>
    <td>T7</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
  </tr>
</table>


<p>APFD serves as a metric to evaluate the effectiveness of the prioritization strategy by calculating the average percentage of faults detected across the prioritized test cases.</p>

![image](https://github.com/CodeReformer/MOTCP/assets/156921147/1b5c30f1-71cb-4153-b4c0-e404e977f2eb)


<p>The eight test cases serve as input to the prioritization algorithm, where the proposed fitness functions come into play. The fitness functions are designed to evaluate and assign priorities to test cases based on multiple criteria, such as historical sensitivity to faults, execution cost, and the overall impact on fault detection. This holistic approach ensures that the prioritization is not solely based on one factor but considers a combination of relevant aspects.</p>

![image](https://github.com/CodeReformer/MOTCP/assets/156921147/869feba2-40d6-4d1c-81e0-d789be17356d)
<br><i>APFD of testcase order T0.</i>



<table border="1">
  <caption>Table 2: Testcases v/s Class matrix</caption>
  <tr>
    <th></th>
    <th>C1</th>
    <th>C2</th>
    <th>C3</th>
    <th>C4</th>
    <th>C5</th>
    <th>C6</th>
    <th>C7</th>
    <th>Wt</th>
  </tr>
  <tr>
    <td>T0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>7</td>
  </tr>
  <tr>
    <td>T1</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>8</td>
  </tr>
  <tr>
    <td>T2</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>8</td>
  </tr>
  <tr>
    <td>T3</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>10</td>
  </tr>
  <tr>
    <td>T4</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>5</td>
  </tr>
  <tr>
    <td>T5</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>8</td>
  </tr>
  <tr>
    <td>T6</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>9</td>
  </tr>
  <tr>
    <td>T7</td>
    <td>1</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>6</td>
  </tr>
  <tr>
    <td>Wc</td>
    <td>6</td>
    <td>5</td>
    <td>7</td>
    <td>8</td>
    <td>5</td>
    <td>9</td>
    <td>5</td>
    <td></td>
  </tr>
</table>



<table border="1">
  <caption>Table 3: Optimal Solution generated from permutated testcases</caption>
  <tr>
    <th>Objectives</th>
    <th>APFD</th>
    <th>SI</th>
    <th>Cost</th>
    <th>Test Cases Order</th>
    <th>Truncated Order</th>
    <th>Reduced Cost</th>
  </tr>
  <tr>
    <td>APFD</td>
    <td>79.464286</td>
    <td>2180.5</td>
    <td>741</td>
    <td>2, 5, 4, 0, 3, 1, 6, 7</td>
    <td>2, 5, 4, 0</td>
    <td>77</td>
  </tr>
  <tr>
    <td>SI</td>
    <td>74.107143</td>
    <td>2802.5</td>
    <td>743</td>
    <td>4, 7, 5, 3, 0, 2, 1, 6</td>
    <td>4, 7, 5, 3, 0, 2</td>
    <td>127</td>
  </tr>
  <tr>
    <td>Cost</td>
    <td>59.821429</td>
    <td>1995.5</td>
    <td>656</td>
    <td>0, 4, 1, 6, 7, 2, 5, 3</td>
    <td>0, 4, 1, 6, 7, 2, 5</td>
    <td>134</td>
  </tr>
</table>



<table border="1">
  <caption>Table 4: Performance comparison of various state-of-art algorithms with optimal solutions</caption>
  <tr>
    <th>Methods</th>
    <th>APFD</th>
    <th>SI</th>
    <th>Cost</th>
    <th>Test Cases Order</th>
    <th>Truncated Order</th>
    <th>Reduced Cost</th>
  </tr>
  <tr>
    <td>NSGA-2 (APFD)</td>
    <td>79.46</td>
    <td>2171.5</td>
    <td>699</td>
    <td>4, 5, 2, 0, 1, 6, 7, 3</td>
    <td>4, 5, 2, 0</td>
    <td>77</td>
  </tr>
  <tr>
    <td>NSGA-2 (SI)</td>
    <td>74.1071</td>
    <td>2788.5</td>
    <td>750</td>
    <td>7, 4, 5, 3, 0, 2, 6, 1</td>
    <td>7, 4, 5, 3, 0, 2</td>
    <td>127</td>
  </tr>
  <tr>
    <td>NSGA-2 (Cost)</td>
    <td>67.85</td>
    <td>1936.5</td>
    <td>664</td>
    <td>4, 0, 1, 2, 6, 5, 7, 3</td>
    <td>4, 0, 1, 2, 6, 5</td>
    <td>113</td>
  </tr>
</table>





<p>To validate the proposed model, the project includes experiments on five handcrafted and three benchmark Java-based applications. The evaluation involves comparing the performance of the NSGA-2 algorithm with various state-of-the-art algorithms commonly used in test case prioritization. The comparison aims to assess the effectiveness, efficiency, and overall superiority of the proposed approach in identifying and addressing faults in software.</p>
<table border="1">
  <caption>Table 5: Handcrafted Dataset</caption>
  <tr>
    <th>Projects</th>
    <th>Versions</th>
    <th>Classes</th>
    <th>LOC</th>
    <th>Functions</th>
    <th>Test cases</th>
    <th>Faults</th>
  </tr>
  <tr>
    <td>P1</td>
    <td>4</td>
    <td>23</td>
    <td>4238</td>
    <td>72</td>
    <td>188</td>
    <td>65</td>
  </tr>
  <tr>
    <td>P2</td>
    <td>4</td>
    <td>16</td>
    <td>2147</td>
    <td>67</td>
    <td>172</td>
    <td>60</td>
  </tr>
  <tr>
    <td>P3</td>
    <td>4</td>
    <td>18</td>
    <td>3454</td>
    <td>79</td>
    <td>204</td>
    <td>75</td>
  </tr>
  <tr>
    <td>P4</td>
    <td>4</td>
    <td>21</td>
    <td>4026</td>
    <td>74</td>
    <td>192</td>
    <td>70</td>
  </tr>
  <tr>
    <td>P5</td>
    <td>4</td>
    <td>26</td>
    <td>5631</td>
    <td>91</td>
    <td>236</td>
    <td>80</td>
  </tr>
</table>

<table border="1">
  <caption>Table 6: Different versions of project1</caption>
  <tr>
    <th>Projects</th>
    <th>Versions</th>
    <th>Classes</th>
    <th>KLOC</th>
    <th>Functions</th>
    <th>Test cases</th>
    <th>Faults</th>
  </tr>
  <tr>
    <td>P1</td>
    <td>V1</td>
    <td>26</td>
    <td>4937</td>
    <td>79</td>
    <td>202</td>
    <td>70</td>
  </tr>
  <tr>
    <td>P1</td>
    <td>V2</td>
    <td>28</td>
    <td>5248</td>
    <td>82</td>
    <td>210</td>
    <td>75</td>
  </tr>
  <tr>
    <td>P1</td>
    <td>V3</td>
    <td>31</td>
    <td>5641</td>
    <td>88</td>
    <td>225</td>
    <td>80</td>
  </tr>
</table>

<table border="1">
  <caption>Table 7: Different versions of project2</caption>
  <tr>
    <th>Projects</th>
    <th>Versions</th>
    <th>Classes</th>
    <th>LOC</th>
    <th>Functions</th>
    <th>Test cases</th>
    <th>Faults</th>
  </tr>
  <tr>
    <td>P2</td>
    <td>V1</td>
    <td>20</td>
    <td>3079</td>
    <td>74</td>
    <td>194</td>
    <td>65</td>
  </tr>
  <tr>
    <td>P2</td>
    <td>V2</td>
    <td>22</td>
    <td>3414</td>
    <td>81</td>
    <td>213</td>
    <td>70</td>
  </tr>
  <tr>
    <td>P2</td>
    <td>V3</td>
    <td>23</td>
    <td>3576</td>
    <td>86</td>
    <td>221</td>
    <td>75</td>
  </tr>
</table>

<table border="1">
  <caption>Table 8: Different versions of project3</caption>
  <tr>
    <th>Projects</th>
    <th>Versions</th>
    <th>Classes</th>
    <th>KLOC</th>
    <th>Functions</th>
    <th>Test cases</th>
    <th>Faults</th>
  </tr>
  <tr>
    <td>P3</td>
    <td>V1</td>
    <td>21</td>
    <td>4186</td>
    <td>86</td>
    <td>224</td>
    <td>80</td>
  </tr>
  <tr>
    <td>P3</td>
    <td>V2</td>
    <td>24</td>
    <td>4654</td>
    <td>92</td>
    <td>233</td>
    <td>85</td>
  </tr>
  <tr>
    <td>P3</td>
    <td>V3</td>
    <td>26</td>
    <td>4882</td>
    <td>97</td>
    <td>246</td>
    <td>90</td>
  </tr>
</table>

<table border="1">
  <caption>Table 9: Different versions of project4</caption>
  <tr>
    <th>Projects</th>
    <th>Versions</th>
    <th>Classes</th>
    <th>LOC</th>
    <th>Functions</th>
    <th>Test cases</th>
    <th>Faults</th>
  </tr>
  <tr>
    <td>P4</td>
    <td>V1</td>
    <td>23</td>
    <td>4603</td>
    <td>81</td>
    <td>208</td>
    <td>75</td>
  </tr>
  <tr>
    <td>P4</td>
    <td>V2</td>
    <td>25</td>
    <td>5019</td>
    <td>85</td>
    <td>215</td>
    <td>80</td>
  </tr>
  <tr>
    <td>P4</td>
    <td>V3</td>
    <td>27</td>
    <td>5418</td>
    <td>91</td>
    <td>234</td>
    <td>85</td>
  </tr>
</table>

<table border="1">
  <caption>Table 10: Different versions of project5</caption>
  <tr>
    <th>Projects</th>
    <th>Versions</th>
    <th>Classes</th>
    <th>LOC</th>
    <th>Functions</th>
    <th>Test cases</th>
    <th>Faults</th>
  </tr>
  <tr>
    <td>P5</td>
    <td>V1</td>
    <td>28</td>
    <td>6328</td>
    <td>98</td>
    <td>251</td>
    <td>85</td>
  </tr>
  <tr>
    <td>P5</td>
    <td>V2</td>
    <td>31</td>
    <td>6636</td>
    <td>103</td>
    <td>264</td>
    <td>90</td>
  </tr>
  <tr>
    <td>P5</td>
    <td>V3</td>
    <td>33</td>
    <td>7345</td>
    <td>109</td>
    <td>283</td>
    <td>95</td>
  </tr>
</table>






![image](https://github.com/CodeReformer/MOTCP/assets/156921147/7bb7c9f6-78b9-43c5-8d84-7828235b6dca)
<br><i>Box plot of different algorithms on (a) P1, (b) P2, (c) P3, (d) P4 dataset.</i>


![image](https://github.com/CodeReformer/MOTCP/assets/156921147/34e6fae5-b82e-4495-a552-5a589901c7b2)
<br><i>Box plot of different algorithms on (a) P5, (b) Ant, (c) jmeter  (d) jtopas dataset.</i>





![image](https://github.com/CodeReformer/MOTCP/assets/156921147/1ba3073e-a271-4419-855b-ccdadd1d5917)

<br><i>Convergence of NSGA-2 on each iteration</i>

![image](https://github.com/CodeReformer/MOTCP/assets/156921147/64000482-a69e-473c-9651-250216879ae7)

<br><i>3D scatter plots that show the first three fronts of NSGA-2.</i>







