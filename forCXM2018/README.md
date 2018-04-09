# for Xiaoming CHEN

## 1. GRETNA

Preprocess subjects data with Gretna 2.0:
- DICOM to Nifti
- (n) Remove first images: 10
- (a) Slice timeing: 2s; plus direction(start at odd);Middle slice
- (r) Reliagn: first
- (w) Normalize: T1; other with default
- (s) Smooth: 6 6 6

Althought follow steps were done, the results were not use.
- (d) Detrend: Linear and Quadratic
- Regress: global - false
- Temporally Filter: 2s; [0.01 0.1]
- Scrubbing: Linear Interpolation; other defautl
- Dynamic Correlation: AAL116_3mm.nii; TRUE; 50; 2

## 2. Exclude Subjects

###14tibet

1. 头动去除的被试（>2mm）

- 1437mabo
- 1450huofangfang
- 1454zhangqian
- 1455yumingxin

2. 配准不好的去掉

- 1449weijuanning

3. 功能像有伪影的去掉

4. 结构项有伪影的去掉

- 1451

### 16tibet——Bold3.0

1. 头动去除的被试（>2mm）

- 1606mayong
- 1620wanyu
- 1634lishaocong
- 1665zhengzhe

2. 配准不好的去掉


## 3. Group ICA

number of components: 28

## 4. Use template to fit Components

templates came from http://www.fmrib.ox.ac.uk/datasets/brainmap+rsns/

select 
- frontoparietal_left(13)
- frontoparietal_right(23)
- DMN前部子网络(18)
- DMN后部子网络(26)
- executive control(22)
- visual(27)

## 5. One sample test & Two sample test performed using group ICA

Utility -> SPM stats



## Others

1. 部分被试的序列长度不同，GroupICA可以计算，但是不知道有没有问题
2. Smith 2009的论文需要再读
3. 需要再看看GroupICA的manual，确认双样本t检验没有问题