### Data flow graph

![Untitled Diagram.drawio(2)](/home/akram/Downloads/Untitled Diagram.drawio(2).png)

### Def-use sets per statement

| Line # | DEF        | USE           |
| ------ | ---------- | ------------- |
| 66     | {total}    | {}            |
| 67     | {rowCount} | {}            |
| 68     | {r}        | {r, rowCount} |
| 69     | {n}        | {r}           |
| 70     | {}         | {n}           |
| 71     | {total}    | {total, n}    |
| 72     | {}         | {}            |
| 74     | {}         | {}            |

### DU-pairs per variable



1. **`total`**

   1. du(66, 71,  total) = {
      	[66, 67, 68, 69, 70, 71, 72, 74]

      }
      
   2. du(71, 71, total) = {
      	[66, 67, 68, 69, 70, 71, 72, 74]

      }

2. **`rowCount`**

   1. du(67, 68, rowCount) = {
      	[66, 67, 68, 74],
      	[66, 67, 68, 69, 70, 72, 74],
      	[66, 67, 68, 69, 70, 71, 72, 74]
      }
   
3. **`r`**

   1. du(68, 68, r) = {
      	[66, 67, 68, 74],
      	[66, 67, 68, 69, 70, 72, 74],
      	[66, 67, 68, 69, 70, 71, 72, 74]
      }
   2. du(68, 69, r) = {
      	[66, 67, 68, 69, 70, 72, 74],
      	[66, 67, 68, 69, 70, 71, 72, 74]
      }
   
4. **`n`**

   1. du(69, 70, n) = {
      	[66, 67, 68, 69, 70, 72, 74],
      	[66, 67, 68, 69, 70, 71, 72, 74]
      }
   2. du(69, 71, n) = {
      	[66, 67, 68, 69, 70, 71, 72, 74]
      }


### for each test case show which pairs are covered

| Test Case                                                    | Lines Covered                    | DU-pairs covered                                             |
| ------------------------------------------------------------ | -------------------------------- | ------------------------------------------------------------ |
| test_calculateColumnTotal_AllPositive()                      | [66, 67, 68, 69, 70, 71, 72, 74] | du(66, 71,  total)<br />du(71, 71,  total)<br />du(67, 68, rowCount)<br />du(68, 68, r)<br />du(68, 69, r)<br />du(69, 70, n)<br />du(69, 71, n) |
| test_calculateColumnTotal_AllNegative()                      | [66, 67, 68, 69, 70, 71, 72, 74] | du(66, 71,  total)<br />du(71, 71,  total)<br />du(67, 68, rowCount)<br />du(68, 68, r)<br />du(68, 69, r)<br />du(69, 70, n)<br />du(69, 71, n) |
| test_calculateColumnTotal_MixedValues()                      | [66, 67, 68, 69, 70, 71, 72, 74] | du(66, 71,  total)<br />du(71, 71,  total)<br />du(67, 68, rowCount)<br />du(68, 68, r)<br />du(68, 69, r)<br />du(69, 70, n)<br />du(69, 71, n) |
| test_calculateColumnTotal_InvalidInput()                     | [66, 67, 68, 69, 70, 72, 74]     | du(67, 68, rowCount)<br />du(68, 68, r)<br />du(68, 69, r)<br />du(69, 70, n) |
| test_calculateColumnTotal_ExceptionThrows<br/>_InvalidParameterException() | [66]                             | None                                                         |



### calculate the DU-Pair coverage.

$$
\begin{align*}
Coverage &= \frac {\text {DU-pairs covered}} {\text {Total DU-pairs}} \\
&= \frac {7} {7} \\
&= 100\%
\end{align*}
$$

