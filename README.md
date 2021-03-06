# -Collaborative-Filtering
Ratings Matrix 페이스북의 팬 페이지를 평가하거나 특정 쇼핑 웹사이트의 제품을 리뷰할 때 일반적으로 1에서 5 또는 1에서 7 사이의 점수를 가진 평가 형식의 리뷰가 있습니다. 우리는 제품에 대한 이러한 사용자 리뷰를 기반으로 합니다. 사용자에게 쇼핑 제안을 할 수 있습니다. 우리가 얻는 평가의 예는 다음과 같습니다.
User/Item	0	1	2	3	4	5
       0	7	6	7	4	5	4
       1	6	7	?	4	3	4
       2	?	3	3	1	1	?
       3	1	2	2	3	3	4
       4	1	?	2	2	3	3
    
    여기서 물음표는 사용자가 제품에 대해 평가하지 않은 등급을 나타내며, 우리의 임무는 이러한 물음표의 값을 예측하는 것입니다. 예측값이 높으면 사용자가 제품을 좋아할 확률이 높고 사용자에게 추천합니다.


사용자 기반 협업 필터링의 아이디어
사용자 기반 협업 필터링의 기본 아이디어는 다음과 같습니다.

사용자 A의 과거에 이 사람이 XYZ 운동화, UVT 모자, MNP 선글라스를 좋아했다고 가정합니다. B의 과거와 마찬가지로 B도 XYZ 운동화와 UVT 모자를 좋아합니다. A는 MNP 선글라스를 더 좋아하고 B도 이 MNP 브랜드 선글라스를 좋아할 가능성이 높으므로 이 두 제품의 선호도가 매우 유사하므로 B에게 이 제품을 구매하도록 제안합니다.
구현 방법
제품 ii에 대한 사용자 uu의 선호도를 예측하기 위해 수행해야 하는 작업은 다음과 같은 2단계로 구성됩니다.

먼저, 우리는 이미 가지고 있는 평가를 통해 이 사용자 uu와 같은 관심사를 공유하는 사람들의 그룹을 찾아야 합니다.
그런 다음 우리가 찾은 uu와 비슷한 관심을 가진 사람들의 그룹과 제품 ii에 대한 이 그룹의 등급을 기반으로 제품 ii에 대한 uu 사용자의 등급을 예측합니다.

코딩:
import numpy as 

nan = np.nan 
ratings_matrix = np.array([[7, 6, 7, 4, 5, 4], 
                           [6, 7, nan, 4, 3, 4],
                           [nan, 3, 3, 1, 1, nan],
                           [1, 2, 2, 3, 3, 4],
                           [1, nan, 1, 2, 3, 3]])
