# SEIR Forecast

#### Author: Yijun Wang, Owen Xu
#### Date: 2020-02-14
#### Last Update: 2020-02-14

### Usage
- Download my Jupyter notebook file: [SEIR.ipynb](https://github.com/yijunwang0805/YijunWang/blob/master/SEIR%20Forecast_Yijun%20Wang%20%26%20Owen%20Xu/SEIR.ipynb)

### Conclusion
- Current policy reduce the number of infectious, while slightly prolong the peak point and thus the duration of the epidemic

### Results
| Cities | Pre-Intervention Peak Point Infectious (million) | Pre-Intervention Peak Point | Current Trending Peak Point Infectious (million) | Current Trending Peak Point |
| --- | --- | --- | --- | --- |
| Wuhan | 132 | 2020-05-25 | 97 | 2020-06-28 |
| Beijing | 543 | 2020-04-02 | 489 | 2020-04-14 |
| Shanghai | 792 | 2020-03-23 | 736 | 2020-04-02 |
| Guangzhou | 601 | 2020-04-04 | 547 | 2020-04-17 |

### Background
-  There has been a novel coronavirus (2019-nCoV) pneumonia outbreak in China since December 2019 which spreads internationally. This study seeks to forecast the number of infectious before and after the intervention

### Parameters
- Initial R0 takes the value of 3.0, while research varies from 1.4 to 3.9 (WHO, 2020; Zhou, 2020; Read, 2020)
  * [WHO](https://www.who.int/news-room/detail/23-01-2020-statement-on-the-meeting-of-the-international-health-regulations-(2005)-emergency-committee-regarding-the-outbreak-of-novel-coronavirus-(2019-ncov))'s preliminary estimate of R<sub>0</sub> is in the range of 1.4 to 2.5 
  * [Zhou, et al](https://arxiv.org/abs/2001.10530) estimates basic reproduction number falls between 2.8 to 3.9 
  * Read, et al's [Novel coronavirus 2019-nCoV: early estimation of epidemiological parameters and epidemic predictions](https://www.medrxiv.org/content/10.1101/2020.01.23.20018549v2.article-info) estimates R<sub>0</sub> to be 3.11
  * [Zhao](https://www.ijidonline.com/article/S1201-9712(20)30053-9/fulltext) estimates that the mean R0 ranges from 2.24 to 3.58
- Trending R0 refers to model ["Estimation of R0"](https://github.com/yijunwang0805/YijunWang/tree/master/Estimation%20of%20R0_Yijun). Value is taken at datetime 8:42 am 02-14-2020
- Wuhan population refers to [The Economic Observer](https://baijiahao.baidu.com/s?id=1656943894281117716&wfr=spider&for=pc)
- Beijing population refers to [World Population Review](http://worldpopulationreview.com/world-cities/beijing/) 
- Shanghai population refers to [World Population Review](http://worldpopulationreview.com/world-cities/shanghai/)

### Fact
- On 2019-12-01, the first case of nCoV exhibits symptons, according to Huang's [Clinical features of patients infected with 2019 novel coronavirus in Wuhan, China](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(20)30183-5/fulltext#seccestitle10). This date is used as the first day of the epidemic.
- On 2020-1-23, Wuhan city lockdowns [(ifeng news)](http://news.ifeng.com/c/7tpL47zV2Vy). Before Wuhan lockdown, 5 million people leave the city [(Tencent News)](https://new.qq.com/sv1/qd/aoyou.html?cmsid=20200127A0EFXJ00)
- There is a time lag between onset of symptons and case confirmed, particularly due to staff and medical supply shortage
- The median time from onset of symptoms to first hospital admission was 7 days, according to Huang's [Clinical features of patients infected with 2019 novel coronavirus in Wuhan, China](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(20)30183-5/fulltext#seccestitle10) (2020).
- After the Wuhan outbreak, people quaratine at home if their cases are not severe, which is a common practice to avoid cross-infection. 

### Assumption
- Assume number of infectious on Jan 23, 2020 is equivalent to the confirm counts on Jan 23, 2020
- Assume homogeneous features across cities
- Assume that infected individuals were not infectious during the incubation period (Zhou, 2020)
- Assume close environment for each individual city
- Assume population growth and death rate are zero

### Limitation
- Due to medical supply and hospital bed shortage, the real number of infectious is not proportionately reflected by the number of confirm counts
- Assumption of homogeneous feature across city

### Disclaimer
- Data uses API from [BlankerL](https://github.com/BlankerL/DXY-COVID-19-Crawler), which is an infection data realtime crawler. The data source is [Ding Xiang Yuan](https://3g.dxy.cn/newh5/view/pneumonia).

### Reference
1. Li, Q., Guan, X., et al. (2020, January 29). [Early Transmission Dynamics in Wuhan, China, of Novel Coronavirus–Infected Pneumonia](https://www.nejm.org/doi/full/10.1056/NEJMoa2001316#article_references). The New England Journal of Medicine. 

2. Wu, Joseph T., et al. (2020, January 28). [Nowcasting and Forecasting the potential domestic and International Spread of the 2019-nCoV Outbreak Originating in Wuhan, China: a Modeling Study](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(20)30260-9/fulltext). Lancet.

3. Zhou Tao, Liu, Y., et al. (2020, January 29). [Preliminary Prediction of the Basic Repreduction Number of the Novel Coronavirus 2019-nCoV](http://kns.cnki.net/kcms/detail/51.1656.r.20200204.1640.002.html)

4. Althaus, Christian L. (2014, June). Estimating the Reproduction Number of Ebola Virus (EBOV) During the 2014 Outbreak in West Africa. PLoS Currents. PMC 4169395. PMID 25642364.

5. Gerardo Chowell, Carlos, P., et al. (2004, July). Model Parameters and Outbreak Control for SARS.

Beijing Population. (2019-05-12). Retrieved 2020-02-14, from http://worldpopulationreview.com/world-cities/beijing/

Shanghai Population. (2019-05-12). Retrieved 2020-02-14, from http://worldpopulationreview.com/world-cities/shanghai/

