---
layout: default
---


# Abstract

Many mispronunciation detection and diagnosis (MD&D) research approaches try to exploit both the acoustic and linguistic features as input. Yet the improvement of the performance is limited, partially due to the shortage of large amount annotated training data at the phoneme level. Phonetic embeddings, extracted from ASR models trained with huge amount of word level annotations, can serve as a good representation of the content of input speech, in a noise-robust and speaker-independent manner. These embeddings, when used as implicit phonetic supplementary information, can alleviate the data shortage of explicit phoneme annotations. We propose to utilize Acoustic, Phonetic and Linguistic (APL) embedding features jointly for building a more powerful MD&D system. Experimental results obtained on the L2-ARCTIC database show the proposed approach outperforms the baseline by 9.93%, 10.13% and 6.17% on the detection accuracy, diagnosis error rate and the F-measure, respectively.


# Experiments

## Phoneme Recognition
### Correctness and Accuracy
| Models        | Correctness| Accuracy |
|:--------------|:-----------:|:--------:|
| Baseline-1    | 71.95%     | 70.25%  |
| Baseline-2 (AL)| 73.21%     | 71.22%  |
| PL-1          | 82.18%     | 80.47%  |
| PL-2          | 81.11%     | 79.56%  |
| APL-1         | 81.49%     | 79.65%  |
| APL-2         | 84.85%     | 83.04%  |

### Confusion Matrix

#### Confusion matrix of frequently misrecognized vowels

<table>
<thead>
  <tr>
    <th></th>
    <th></th>
    <th colspan="6">Annotation</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td></td>
    <td></td>
    <td>aa</td>
    <td>ah</td>
    <td>ae</td>
    <td>eh</td>
    <td>ih</td>
    <td>iy</td>
  </tr>
  <tr>
    <td rowspan="6">Baseline-2 (AL)</td>
    <td>aa</td>
    <td>220</td>
    <td>63</td>
    <td>10</td>
    <td>2</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>ah</td>
    <td>31</td>
    <td>2025</td>
    <td>23</td>
    <td>23</td>
    <td>104</td>
    <td>13</td>
  </tr>
  <tr>
    <td>ae</td>
    <td>10</td>
    <td>64</td>
    <td>617</td>
    <td>63</td>
    <td>16</td>
    <td>1</td>
  </tr>
  <tr>
    <td>eh</td>
    <td>1</td>
    <td>95</td>
    <td>58</td>
    <td>534</td>
    <td>79</td>
    <td>7</td>
  </tr>
  <tr>
    <td>ih</td>
    <td>0</td>
    <td>128</td>
    <td>1</td>
    <td>32</td>
    <td>1212</td>
    <td>183</td>
  </tr>
  <tr>
    <td>iy</td>
    <td>0</td>
    <td>23</td>
    <td>1</td>
    <td>8</td>
    <td>184</td>
    <td>1043</td>
  </tr>
  <tr>
    <td rowspan="6">AL-2</td>
    <td>aa</td>
    <td>239</td>
    <td>51</td>
    <td>14</td>
    <td>2</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>ah</td>
    <td>13</td>
    <td>2152</td>
    <td>10</td>
    <td>18</td>
    <td>83</td>
    <td>5</td>
  </tr>
  <tr>
    <td>ae</td>
    <td>12</td>
    <td>41</td>
    <td>660</td>
    <td>56</td>
    <td>14</td>
    <td>0</td>
  </tr>
  <tr>
    <td>eh</td>
    <td>1</td>
    <td>49</td>
    <td>45</td>
    <td>654</td>
    <td>37</td>
    <td>11</td>
  </tr>
  <tr>
    <td>ih</td>
    <td>1</td>
    <td>74</td>
    <td>3</td>
    <td>22</td>
    <td>1399</td>
    <td>130</td>
  </tr>
  <tr>
    <td>iy</td>
    <td>0</td>
    <td>13</td>
    <td>0</td>
    <td>3</td>
    <td>174</td>
    <td>1138</td>
  </tr>
  <tr>
    <td rowspan="6">APL-2</td>
    <td>aa</td>
    <td>290</td>
    <td>18</td>
    <td>11</td>
    <td>3</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>ah</td>
    <td>8</td>
    <td>2298</td>
    <td>11</td>
    <td>10</td>
    <td>19</td>
    <td>12</td>
  </tr>
  <tr>
    <td>ae</td>
    <td>5</td>
    <td>39</td>
    <td>728</td>
    <td>16</td>
    <td>4</td>
    <td>0</td>
  </tr>
  <tr>
    <td>eh</td>
    <td>0</td>
    <td>41</td>
    <td>34</td>
    <td>710</td>
    <td>17</td>
    <td>15</td>
  </tr>
  <tr>
    <td>ih</td>
    <td>0</td>
    <td>35</td>
    <td>0</td>
    <td>15</td>
    <td>1526</td>
    <td>89</td>
  </tr>
  <tr>
    <td>iy</td>
    <td>0</td>
    <td>17</td>
    <td>0</td>
    <td>2</td>
    <td>147</td>
    <td>1185</td>
  </tr>
</tbody>
</table>

#### Confusion matrix of frequently misrecognized consonants

<table>
<thead>
  <tr>
    <th></th>
    <th></th>
    <th colspan="6">Annotation</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td></td>
    <td></td>
    <td>d</td>
    <td>dh</td>
    <td>t</td>
    <td>sh</td>
    <td>s</td>
    <td>z</td>
  </tr>
  <tr>
    <td rowspan="6">Baseline-2 (AL)</td>
    <td>d</td>
    <td>1085</td>
    <td>104</td>
    <td>107</td>
    <td>1</td>
    <td>6</td>
    <td>3</td>
  </tr>
  <tr>
    <td>dh</td>
    <td>149</td>
    <td>104</td>
    <td>20</td>
    <td>0</td>
    <td>3</td>
    <td>0</td>
  </tr>
  <tr>
    <td>t</td>
    <td>141</td>
    <td>4</td>
    <td>1212</td>
    <td>0</td>
    <td>12</td>
    <td>1</td>
  </tr>
  <tr>
    <td>sh</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>324</td>
    <td>3</td>
    <td>0</td>
  </tr>
  <tr>
    <td>s</td>
    <td>2</td>
    <td>0</td>
    <td>6</td>
    <td>20</td>
    <td>1485</td>
    <td>83</td>
  </tr>
  <tr>
    <td>z</td>
    <td>2</td>
    <td>0</td>
    <td>1</td>
    <td>6</td>
    <td>180</td>
    <td>247</td>
  </tr>
  <tr>
    <td rowspan="6">AL-2</td>
    <td>d</td>
    <td>1159</td>
    <td>185</td>
    <td>74</td>
    <td>0</td>
    <td>6</td>
    <td>4</td>
  </tr>
  <tr>
    <td>dh</td>
    <td>106</td>
    <td>202</td>
    <td>9</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
  </tr>
  <tr>
    <td>t</td>
    <td>95</td>
    <td>13</td>
    <td>1337</td>
    <td>3</td>
    <td>11</td>
    <td>3</td>
  </tr>
  <tr>
    <td>sh</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>327</td>
    <td>4</td>
    <td>1</td>
  </tr>
  <tr>
    <td>s</td>
    <td>0</td>
    <td>0</td>
    <td>7</td>
    <td>4</td>
    <td>1410</td>
    <td>204</td>
  </tr>
  <tr>
    <td>z</td>
    <td>1</td>
    <td>0</td>
    <td>3</td>
    <td>0</td>
    <td>121</td>
    <td>346</td>
  </tr>
  <tr>
    <td rowspan="6">APL-2</td>
    <td>d</td>
    <td>1187</td>
    <td>230</td>
    <td>33</td>
    <td>0</td>
    <td>5</td>
    <td>2</td>
  </tr>
  <tr>
    <td>dh</td>
    <td>104</td>
    <td>215</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
  </tr>
  <tr>
    <td>t</td>
    <td>74</td>
    <td>9</td>
    <td>1379</td>
    <td>0</td>
    <td>8</td>
    <td>1</td>
  </tr>
  <tr>
    <td>sh</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>327</td>
    <td>4</td>
    <td>0</td>
  </tr>
  <tr>
    <td>s</td>
    <td>0</td>
    <td>0</td>
    <td>3</td>
    <td>1</td>
    <td>1479</td>
    <td>125</td>
  </tr>
  <tr>
    <td>z</td>
    <td>0</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>141</td>
    <td>325</td>
  </tr>
</tbody>
</table>

### Phonemes that APL Most Improve on (PL vs. APL)
With taking acoustic features,  the top 5 phonemes benefited are 'aa',  'jh',  'ao',  'ae' and 'uh',  which get 21.24%, 14.29%, 12.14%, 10.30% and 10.24% relative improvements in accuracy, respectively.  Most of them are vowels.

## Mispronunciation Detection and Diagnosis
### Performance Accross Models
<table>
<thead>
  <tr>
    <th>Models</th>
    <th>FRR</th>
    <th>FAR</th>
    <th>Detection Rate</th>
    <th>Diagnosis Error Rate</th>
    <th>Recall</th>
    <th>Precision</th>
    <th>F-measure</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Baseline-1</td>
    <td>24.45%</td>
    <td>24.81%</td>
    <td>74.81%</td>
    <td>44.14%</td>
    <td>74.19%</td>
    <td>34.70%</td>
    <td>47.28%</td>
  </tr>
  <tr>
    <td>Baseline-2 (AL)</td>
    <td>24.19%</td>
    <td>27.60%</td>
    <td>75.66%</td>
    <td>44.07%</td>
    <td>72.40%</td>
    <td>35.29%</td>
    <td>47.45%</td>
  </tr>
  <tr>
    <td>PL-1</td>
    <td>12.12%</td>
    <td>41.83%</td>
    <td>83.31%</td>
    <td>37.67%</td>
    <td>58.17%</td>
    <td>46.66%</td>
    <td>51.78%</td>
  </tr>
  <tr>
    <td>PL-2</td>
    <td>13.55%</td>
    <td>39.43%</td>
    <td>82.63%</td>
    <td>37.64%</td>
    <td>60.57%</td>
    <td>44.89%</td>
    <td>51.57%</td>
  </tr>
  <tr>
    <td>APL-1</td>
    <td>13.57%</td>
    <td>38.01%</td>
    <td>82.84%</td>
    <td>37.89%</td>
    <td>61.99%</td>
    <td>45.43%</td>
    <td>52.44%</td>
  </tr>
  <tr>
    <td>APL-2</td>
    <td>8.88%</td>
    <td>45.51%</td>
    <td>85.59%</td>
    <td>33.94%</td>
    <td>54.49%</td>
    <td>52.79%</td>
    <td>53.62%</td>
  </tr>
</tbody>
</table>

### Mispronunciations Hardest to Detect across Different Accents
<table>
<thead>
  <tr>
    <th>Mother Tongue</th>
    <th>Top 3 Mispronunciations</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Arabic</td>
    <td>(r, r*); (ih, eh); (ow, ao)</td>
  </tr>
  <tr>
    <td>Hindi</td>
    <td>(t, d); (&lt;eps&gt;, ax); (w, w*)</td>
  </tr>
  <tr>
    <td>Korean</td>
    <td>(v, f); (jh, ch); (aw, aa)</td>
  </tr>
  <tr>
    <td>Mandarin</td>
    <td>(th, t); (d, t); (l, w)</td>
  </tr>
  <tr>
    <td>Spanish</td>
    <td>(ey, eh); (ah, eh); (&lt;eps&gt;, eh)</td>
  </tr>
  <tr>
    <td>Vietnamese</td>
    <td>(ah, ao); (s, z); (ae, eh)</td>
  </tr>
</tbody>
</table>

The top 3 challenge mispronunciations in APL-2 model of the six accents in the test set are show above, in which each mispronunciation is represented in a tuple.  For example, (r, r*) indicates that 'r' is mispronounced with 'r*', and (\< eps\>, ax) stands for an insertion error.  Since for each accent only one speaker is included in the testset, more data is needed to show a more robust trend across the six accents.
