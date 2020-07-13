# Robust Subspace Approaches for Analyzing Incomplete Synchrophasor Measurements
Published in: 9th IFAC Symposium on Control of Power and Energy Systems. For more information, please refer to the paper.

## Abstract
Synchrophasor measurements can significantly enhance the monitorability of the power grid by revealing the dynamics of grid operation. However, due to high-rate samples collected in large volume, big data challenges emerge to efficiently process the data. The present work advocates robust subspace approaches including robust principal component analysis and subspace clustering, to identify low-dimensional structures in the synchrophasor data, even when portions of measurements are missing due to sensor or network issues, and outliers are present in the data. The outliers can model abnormal dynamics or cyber-attacks in the grid. Numerical tests using simulated synchrophasor data illustrate the utility of the approaches.

## Dataset
Synthetic PMU data were generated using the PSS/E simulator [1]. The tested gird containing 20 buses and 6 generators is shown below:

<img src="https://user-images.githubusercontent.com/67979833/87258801-6cde9b80-c474-11ea-8042-cf8c81847f16.png" width=50% height=50%>

Two scenarios were simulated. In Scenario 1, the transmission line connecting buses 3001 and 3003 is tripped at t = 10 sec and then closed at t = 70 sec. In Scenario 2, the line connecting buses 151 and 201 is tripped at t = 100 sec, followed by a trip of the generator at bus 102 at t = 200 sec. Subsequently, the previously tripped line is closed at t = 250 sec. Only the voltage magnitudes are used for simplicity and the voltage magnitudes for both Scenario 1 and Scenario 2 are plotted as follows:

<table align='center'>
<tr align='center'>
<td> Scenario 1 </td>
<td> Scenario 2  </td>
</tr>
<tr>
<td><img width="576" alt="voltmag_case1" src="https://user-images.githubusercontent.com/67979833/87258975-f2168000-c475-11ea-9481-7fc4c5325750.png">
<td><img width="576" alt="voltmag_case2" src="https://user-images.githubusercontent.com/67979833/87258976-f2168000-c475-11ea-8884-75570fe61c29.png">
</tr>
</table>

## Results
### 1. Reconstruction
The figures below show the true and the reconstructed entries of the voltage magnitudes with 1% misses, where the circles indicate the reconstructed versions of the misses.

<table align='center'>
<tr align='center'>
<td> Scenario 1 with robust PCA </td>
<td> Scenario 2 with robust subspace clustering </td>
</tr>
<tr>
<td><img width="576" alt="reconstr_case1_RPCA" src="https://user-images.githubusercontent.com/67979833/87259217-b8df0f80-c477-11ea-93f4-6b454e788de1.png">
<td><img width="576" alt="reconstr_case2_RSC" src="https://user-images.githubusercontent.com/67979833/87259218-b8df0f80-c477-11ea-8679-e72e6aa96fc8.png">
</tr>
</table>

### 2. Outlier (or Abnormality) Detection
The figures below show the performance of outlier detection in the two scenarios tested.

<table align='center'>
<tr align='center'>
<td> Robust PCA for Scenario 1 </td>
<td> Robust PCA for Scenario 2 </td>
<td> Robust subspace clustering for Scenario 1 </td>
<td> Robust subspace clustering for Scenario 2 </td>
</tr>
<tr>
<td><img width="576" alt="sparse_case1_RPCA" src="https://user-images.githubusercontent.com/67979833/87259428-36efe600-c479-11ea-979d-4219e355bd7c.png">
<td><img width="576" alt="sparse_case2_RPCA" src="https://user-images.githubusercontent.com/67979833/87259429-36efe600-c479-11ea-8894-4de87ad9a63c.png">
<td><img width="576" alt="sparse_case1_RSC_v2" src="https://user-images.githubusercontent.com/67979833/87259448-5e46b300-c479-11ea-9a29-5d8556464210.png">
<td><img width="576" alt="sparse_case2_RSC_v2" src="https://user-images.githubusercontent.com/67979833/87259449-5e46b300-c479-11ea-9c2a-e508c087c7c6.png">
</tr>
</table>

## References
[1] Siemens, PSS/E Documentation, Version 33.5, 2013. 

