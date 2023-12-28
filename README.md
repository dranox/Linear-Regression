# Linear-Regression
## Mục lục

1. [Nội dung đồ án](#c1)
    - [Mô tả dữ liệu](#c11)
    - [Yêu cầu](#c12)
2. [Quy định nộp bài](#c2)
3. [Quy định chấm bài](#c3)
## Nội dung đồ án <a class="anchor" id="c1"></a>
Mục tiêu của đồ án là tìm hiểu các yếu tố quyết định mức lương và việc làm của các kỹ sư ngay sau khi tốt nghiệp. Các yếu tố như điểm số ở các cấp/trường đại học, kỹ năng của ứng viên, sự liên kết giữa trường đại học và các khu công nghiệp/công ty công nghệ, bằng cấp của sinh viên và điều kiện thị trường cho các ngành công nghiệp cụ thể sẽ ảnh hưởng đến điều này.

Bộ dữ liệu được sử dụng trong đồ án này thu thập tại Ấn Độ, nơi có hơn 6000 cơ sở đào tạo kỹ thuật công nghệ với khoảng 2,9 triệu sinh viên đang học tập. Mỗi năm, trung bình có 1,5 triệu sinh viên tốt nghiệp chuyên ngành Công nghệ/Kỹ thuật, tuy nhiên do thiếu kỹ năng cần thiết, ít hơn 20% trong số họ có việc làm phù hợp với chuyên môn của mình. Bộ dữ liệu này không chỉ giúp xây dựng công cụ dự đoán mức lương mà còn cung cấp thông tin về các yếu tố ảnh hưởng đến mức lương và chức danh công việc trên thị trường lao động. Sinh viên sẽ được khám phá những thông tin này trong phạm vi đồ án.
### Mô tả dữ liệu <a class="anchor" id="c11"></a>
#### Dữ liệu Mức lương kỹ sư tốt nghiệp đại học
Bộ dữ liệu có 2998 dòng và 34 cột. Ý nghĩa và kiểu dữ liệu của từng cột được thể hiện ở bảng sau:

| Thuộc tính             | Mô tả                                                                      | Kiểu dữ liệu                      |
|------------------------|--------------------------------------------------------------------------------|-----------------------------------|
| ID                     | Mã định danh để xác định ứng viên                                               | String                         |
| Salary                 | Mức lương hàng năm được đề xuất cho ứng viên (tính bằng Indian Rupee)           | Decimal                     |
| Gender                 | Giới tính của ứng viên (Nữ: f; Nam: m)                                       | String                              |
| DOB                    | Ngày sinh của ứng viên (yyyy-mm-dd)                                                        | Date                              |
| 10percentage           | Tổng điểm đạt được trong kỳ thi lớp 10                                         | Decimal              |
| 10board                | Hội đồng trường mà ứng viên theo học trong lớp 10                             | String                              |
| 12graduation           | Năm tốt nghiệp - cuối cấp trung học                                          | Integer                    |
| 12percentage           | Tổng điểm đạt được trong kỳ thi lớp 12                                         | Decimal              |
| 12board                | Hội đồng trường mà ứng viên theo học trong lớp 12                             | String                              |
| CollegeID              | Mã duy nhất nhận diện trường đại học mà ứng viên theo học                     | String                         |
| CollegeTier            | Mỗi trường đại học đã được chú thích là 1 hoặc 2. Quy định bởi điểm trung bình AMCAT đạt được bởi sinh viên tại trường đại học đó. Các trường đại học có điểm trung bình vượt qua ngưỡng cho trước được đánh dấu là 1 và các trường khác là 2. | Integer                   |
| Degree                 | Bằng cấp đã đạt hoặc đang theo học bởi ứng viên                               | String                              |
| Specialization         | Chuyên ngành theo học bởi ứng viên                                           | String                              |
| CollegeGPA             | GPA tổng cộng tại thời điểm tốt nghiệp                                        | Decimal                     |
| CollegeCityID          | Mã định danh của thành phố có trường đại học mà ứng viên theo học                   | String                         |
| CollegeCityTier        | Hạng của thành phố có trường đại học mà ứng viên theo học. Quy định dựa trên dân số của thành phố. | Integer                   |
| CollegeState           | Tên tiểu bang nơi trường đại học đặt tại                                       | String                              |
| GraduationYear         | Năm tốt nghiệp (Bằng cử nhân)                                                 | Integer                    |
| English                | Điểm số trong phần tiếng Anh của AMCAT                                        | Decimal                   |
| Logical                | Điểm số trong phần khả năng lô-gic của AMCAT                                   | Decimal                   |
| Quant                  | Điểm số trong phần khả năng định lượng của AMCAT                              | Decimal                   |
| Domain                 | Điểm số trong mô-đun chuyên ngành của AMCAT                                   | Decimal                   |
| ComputerProgramming    | Điểm số trong phần lập trình máy tính của AMCAT                              | Decimal                   |
| ElectronicsAndSemicon  | Điểm số trong phần Kỹ thuật Điện tử và Bán dẫn của AMCAT                     | Decimal                   |
| ComputerScience        | Điểm số trong phần Khoa học Máy tính của AMCAT                               | Decimal                   |
| MechanicalEngg         | Điểm số trong phần Kỹ thuật Cơ khí của AMCAT                                 | Decimal                   |
| ElectricalEngg         | Điểm số trong phần Kỹ thuật Điện của AMCAT                                    | Decimal                   |
| TelecomEngg            | Điểm số trong phần Kỹ thuật Viễn thông của AMCAT                             | Decimal                   |
| CivilEngg              | Điểm số trong phần Kỹ thuật Xây dựng của AMCAT                               | Decimal                   |
| conscientiousness      | Điểm số trong một trong các phần của bài kiểm tra tính cách AMCAT             | Decimal                   |
| agreeableness          | Điểm số trong một trong các phần của bài kiểm tra tính cách AMCAT             | Decimal                   |
| extraversion           | Điểm số trong một trong các phần của bài kiểm tra tính cách AMCAT             | Decimal                   |
| neuroticism            | Điểm số trong một trong các phần của bài kiểm tra tính cách AMCAT             | Decimal                   |
| openness_to_experience | Điểm số trong một trong các phần của bài kiểm tra tính cách AMCAT             | Decimal                   |


Đọc thêm về dữ liệu tại: [Engineering Graduate Salary](https://www.kaggle.com/datasets/manishkc06/engineering-graduate-salary-prediction).

#### Dữ liệu sử dụng cho đồ án
Trong đồ án này, dữ liệu trên đã được thực hiện các bước tiền xử lý sau:
1. Loại bỏ các cột có giá trị là chuỗi: `DOB`, `10board`, `12board`, `Specialization`, `CollegeState`
5. Loại bỏ các cột liên quan đến định danh và năm: `ID`, `CollegeID`, `CollegeCityID`, `12graduation`, `GraduationYear`

Sau quá trình tiền xử lý, dữ liệu mới có:
- 2998 dòng dữ liệu
- 24 cột dữ liệu gồm:
    - 1 giá trị mục tiêu ($y$): `Salary`
    - 23 đặc trưng giải thích $(X)$ (đặc trưng giúp tìm giá trị mục tiêu) gồm: `Gender`, `10percentage`, `12percentage`, `CollegeTier`, `Degree`, `collegeGPA`, `CollegeCityTier`, `English`, `Logical`, `Quant`, `Domain`, `ComputerProgramming`, `ElectronicsAndSemicon`, `ComputerScience`, `MechanicalEngg`, `ElectricalEngg`, `TelecomEngg`, `CivilEngg`, `conscientiousness`, `agreeableness`, `extraversion`, `nueroticism`, `openess_to_experience`

Sinh viên được cung cấp 2 tập tin:
- `train.csv`: Chứa 2248 mẫu dùng để huấn luyện mô hình
- `test.csv`: Chứa 750 mẫu dùng để kiểm tra mô hình

### Yêu cầu <a class="anchor" id="c12"></a>
Trong đồ án này, sinh viên được yêu cầu thực hiện:

1. Xây dựng mô hình *dự đoán mức lương của kỹ sư* **sử dụng mô hình hồi quy tuyến tính** (7 điểm)
- Yêu cầu 1a: Sử dụng 11 đặc trưng đầu tiên đề bài cung cấp bao gồm: `Gender`, `10percentage`, `12percentage`, `CollegeTier`, `Degree`, `collegeGPA`, `CollegeCityTier`, `English`, `Logical`, `Quant`, `Domain` (2 điểm)
	- Huấn luyện 1 lần duy nhất cho 11 đặc trưng nói trên cho toàn bộ tập huấn luyện (`train.csv`)
	- Thể hiện công thức cho mô hình hồi quy (tính $y$ theo 11 đặc trưng trên)
	- Báo cáo **1 kết quả trên tập kiểm tra (`test.csv`)** cho mô hình vừa huấn luyện được

- Yêu cầu 1b: Phân tích ảnh hưởng của **đặc trưng tính cách** dựa trên điểm các bài kiểm tra của AMCAT (1 điểm)
	- Thử nghiệm lần lượt trên các đặc trưng tính cách gồm: `conscientiousness`, `agreeableness`, `extraversion`, `nueroticism`, `openess_to_experience`
    - Yêu cầu sử dụng **k-fold Cross Validation** (**k** tối thiểu là 5) để tìm ra đặc trưng tốt nhất trong các đặc trưng tính cách
	- Báo cáo **5 kết quả tương ứng cho 5 mô hình** từ k-fold Cross Validation (lấy trung bình)
	
	<center>

	| STT | Mô hình với 1 đặc trưng | MAE  |
	|:---:|:-----------------------:|:----:|
	|  1  | conscientiousness       |      |
	|  2  | agreeableness           |      |
	|  3  | extraversion            |      |
	|  4  | neuroticism             |      |
	|  5  | openness_to_experience  |      |

	</center>

	- Thể hiện công thức cho mô hình hồi quy theo đặc trưng tốt nhất (tính $y$ theo đặc trưng tốt nhất tìm được)
    - Báo cáo **1 kết quả trên tập kiểm tra (`test.csv`)** cho mô hình với đặc trưng tốt nhất tìm được

- Yêu cầu 1c: Phân tích ảnh hưởng của **đặc trưng ngoại ngữ, lô-gic, định lượng** đến mức lương của các kỹ sư dựa trên điểm các bài kiểm tra của AMCAT (1 điểm)

	- Thử nghiệm trên các đặc trưng gồm: `English`, `Logical`, `Quant`
    - Yêu cầu sử dụng **k-fold Cross Validation** (**k** tối thiểu là 5) để tìm ra đặc trưng tốt nhất
	- Báo cáo **3 kết quả tương ứng cho 3 mô hình** từ k-fold Cross Validation (lấy trung bình)
	
	<center>

	| STT | Mô hình với 1 đặc trưng | MAE  |
	|:---:|:-----------------------:|:----:|
	|  1  | English			        |      |
	|  2  | Logical		            |      |
	|  3  | Quant		            |      |

	</center>

	- Thể hiện công thức cho mô hình hồi quy theo đặc trưng tốt nhất (tính $y$ theo đặc trưng tốt nhất tìm được)
    - Báo cáo **1 kết quả trên tập kiểm tra (`test.csv`)** cho mô hình với đặc trưng tốt nhất tìm được
	
- Yêu cầu 1d: Sinh viên tự xây dựng mô hình, tìm mô hình cho kết quả tốt nhất (3 điểm)
	- Xây dựng `m` mô hình khác nhau (tối thiểu 3), đồng thời khác mô hình ở 1a, 1b và 1c
		- Mô hình có thể là sự kết hợp của 2 hoặc nhiều đặc trưng
		- Mô hình có thể sử dụng đặc trưng đã được chuẩn hóa hoặc biến đổi (bình phương, lập phương...)
		- Mô hình có thể sử dụng đặc trưng được tạo ra từ 2 hoặc nhiều đặc trưng khác nhau (cộng 2 đặc trưng, nhân 2 đặc trưng...)
		- ...
	- Gợi ý xây dựng mô hình:
		- Trực quan hóa các biến và đánh giá tính phân phối, tương quan giữa các biến, và xác định các đặc điểm đáng chú ý của dữ liệu
		- Phân tích mối quan hệ giữa biến mục tiêu và các biến dự đoán bằng các biểu đồ phân tán, ma trận tương quan, và biểu đồ histogram
		- $\to$ lựa chọn đặc trưng phù hợp cho mô hình mới

	- Yêu cầu **sử dụng phương pháp k-fold Cross Validation** (**k** tối thiểu là 5) để tìm ra mô hình tốt nhất trong `m` mô hình mà sinh viên xây dựng

	- Báo cáo **`m` kết quả tương ứng cho `m` mô hình** từ k-fold Cross Validation (lấy trung bình)

	<center>

	| STT |           Mô hình          | MAE  |
	|:---:|:--------------------------:|:----:|
	|  1  | Sử dụng 2 đặc trưng (a, b) |      |
	| ... | ...                        |      |
	|  m  | ...                        |      |

	</center>

	- Thể hiện công thức cho mô hình hồi quy tốt nhất mà sinh viên tìm được.
	- Báo cáo **1 kết quả trên tập kiểm tra (`test.csv`)** cho mô hình tốt nhất tìm được


- <ins>Lưu ý:</ins>
    - Kết quả báo cáo là độ đo MAE
	- Ở câu 1d, **mô hình sử dụng 2 đặc trưng** trên đặc trưng (a, b) và (b, c) cũng chỉ được tính là một mô hình sử dụng 2 đặc trưng
    

2. Báo cáo về kết quả, đánh giá và nhận xét các mô hình đã xây dựng (3 điểm)
    - Báo cáo cần có thông tin cá nhân (họ và tên, MSSV), số trang và tài liệu tham khảo (cần chỉ định cụ thể tài liệu được sử dụng cho phần nào trong bài làm)
    - Liệt kê TẤT CẢ thư viện đã sử dụng và lý do sử dụng chúng
	- Liệt kê TẤT CẢ hàm đã sử dụng và mô tả các hàm đó
    - Báo cáo và nhận xét kết quả từ TOÀN BỘ các mô hình xây dựng được (có $1 + (5 + 1) + (3 + 1) + (m + 1)$ kết quả)
    - Với yêu cầu 1b, 1c và 1d: Giải thích hoặc nêu giả thuyết cho mô hình đạt kết quả tốt nhất ở mỗi yêu cầu
	- Với yêu cầu 1d: trình bày toàn bộ quá trình và lý do trích chọn/thiết kế các đặc trưng cho `m` mô hình mà sinh viên xây dựng. Sinh viên có thể sử dụng các thuật toán/phương pháp có sẵn nhưng phải trình bày lại phương pháp đó trong báo cáo
