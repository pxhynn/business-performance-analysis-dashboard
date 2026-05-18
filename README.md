# 📊 Dự Án Phân Tích Hiệu Suất Kinh Doanh Toàn Cầu (Business Performance Analysis)

## 📷 Tổng Quan Dashboard (Dashboard Preview)
![Overview Dashboard](images/dashboard_overview.png)
*Hình 1: Giao diện trực quan của Dashboard Phân tích Hiệu suất Kinh doanh theo Quốc gia và Ngành hàng.*

---

## 📁 Đường Dẫn Kiểm Tra Dự Án (Project Deliverables)
Do chính sách bảo mật hệ thống khóa tính năng mã nhúng trực tuyến (Publish to Web), bạn có thể tiếp cận và đánh giá dự án thông qua 2 cách tối ưu sau:

1. **Xem trực tiếp trên trình duyệt (Nhanh chóng):** 🌐 Xem toàn bộ bố cục sắp xếp và thiết kế trực quan thông qua **[File PDF Báo Cáo Xuất Bản](./Business%20Performance%20Analysis%20Dashboard.pdf)**. GitHub hỗ trợ hiển thị trực tiếp file PDF này giúp bạn đánh giá nhanh tư duy UI/UX mà không cần cài đặt phần mềm.
2. **Trải nghiệm offline đầy đủ tính năng:** 📥 Tải file kĩ thuật gốc **`[PhamXuanHuyen_20.01.2004_TPHCM_K308.pbix]`** có sẵn trong kho lưu trữ này về máy tính để kiểm tra chi tiết cấu trúc mô hình dữ liệu (Data Model), các hàm tính toán DAX nâng cao và quy trình Power Query.

---

## 🎯 Bài Toán Kinh Doanh (Business Case)
* **Bối cảnh:** Một doanh nghiệp bán lẻ đa quốc gia kinh doanh 3 nhóm ngành hàng chính (Phụ kiện, Xe đạp, Quần áo) trên 6 quốc gia (Mỹ, Úc, Anh, Đức, Pháp, Canada) cần một giải pháp quản trị tổng thể để theo dõi sức khỏe tài chính và hiệu suất phân phối.
* **Yêu cầu cốt lõi:** Xây dựng hệ thống Dashboard quản trị tập trung (Executive Tổng quan) nhằm giúp Ban giám đốc xác định rõ:
  * Đâu là thị trường trọng điểm sinh lời?
  * Dòng sản phẩm nào đang đóng góp doanh thu cốt lõi?
  * Xu hướng tăng trưởng theo dòng thời gian (Time-series) diễn biến ra sao để tối ưu hóa chuỗi cung ứng toàn cầu.

---

## 🗃️ Chỉ Số Thống Kê Chủ Chốt (Key Performance Indicators)
Báo cáo ghi nhận các con số tài chính ấn tượng trong giai đoạn tăng trưởng:
* **Tổng Doanh Thu (Total Sales):** \$29.36M 
* **Tổng Lợi Nhuận (Total Profit):** \$12.08M (Tỷ suất lợi nhuận gộp đạt mức rất cao ~41.1%)
* **Tổng Số Lượng Đơn Hàng (Total Orders):** 27.66K đơn hàng
* **Tốc Độ Tăng Trưởng Doanh Thu (YOY Growth %):** Tăng trưởng vượt trội với **49.88%** so với cùng kỳ năm trước.

---

## 🗃️ Kiến Trúc Mô Hình Dữ Liệu (Data Modeling)
* **Quy trình xử lý dữ liệu thô (Power Query):** Chuẩn hóa định dạng chuỗi ngày tháng (Date/Calendar Table), xử lý dữ liệu trống, phân loại danh mục sản phẩm và đồng bộ hóa các trường dữ liệu địa lý (Country, Region) để hiển thị chính xác biểu đồ bản đồ (Map Visual).
* **Mô hình hóa dữ liệu:** Triển khai cấu trúc mô hình tối ưu **Star Schema** (Mô hình sao) giúp tối ưu hóa tốc độ truy vấn DAX, bao gồm bảng dữ liệu thực tế (`Fact_Sales`) kết nối chặt chẽ với các bảng danh mục chiều (`Dim_Products`, `Dim_Countries`, `Dim_Calendar`).

---

## 🛠️ Kỹ Thuật DAX Nâng Cao Đã Sử Dụng
* **Time Intelligence Metrics:** Thiết lập các hàm đo lường thời gian nâng cao để so sánh hiệu suất song song: `Sales This Year` và `Sales Last Year`, từ đó tự động tính toán chính xác tỷ lệ tăng trưởng theo từng năm (YOY Growth %).
* **Nhóm bộ lọc thông minh (Slicers):** Tích hợp bộ lọc động theo Năm (2016 - 2019) và Ngành hàng, cho phép người dùng tương tác sâu và phân rã dữ liệu (Drill-down) chi tiết theo nhu cầu của từng phòng ban.

---

## 💡 Khám Phá Trọng Tâm & Đề Xuất Kinh Doanh (Key Insights & Actionable Recommendations)

### 📊 Phát hiện cốt lõi từ dữ liệu (Key Insights)
1. **Thị trường Mỹ và Úc chiếm vị thế độc tôn:** Hoa Kỳ (United States) và Úc (Australia) là hai thị trường mang lại nguồn lợi nhuận khổng lồ vượt trội hoàn toàn so với nhóm các quốc gia châu Âu (Anh, Đức, Pháp) và Canada.
2. **Nghịch lý Đơn hàng - Lợi nhuận của ngành hàng Bikes (Xe đạp):** * Tại thị trường **Mỹ**, số lượng đơn hàng lớn nhất thuộc về nhóm *Accessories (Phụ kiện)*. Tuy nhiên, khi nhìn sang biểu đồ Lợi nhuận (`Total Profit`), nhóm **Bikes (Xe đạp)** mới là sản phẩm mang lại giá trị lợi nhuận áp đảo chiếm tới hơn 90% tổng lợi nhuận của quốc gia này.
   * Tại thị trường **Úc**, dòng sản phẩm *Bikes* dẫn đầu tuyệt đối trên cả hai phương diện: Lượng đơn hàng đặt nhiều nhất và Lợi nhuận đem về cao nhất.
3. **Xu hướng tăng trưởng bền vững:** Nhìn vào biểu đồ xu hướng theo thời gian, doanh số nửa cuối năm luôn có sự bứt phá mạnh mẽ so với nửa đầu năm. Chu kỳ tăng trưởng này lặp lại liên tục qua các năm, cho thấy tính mùa vụ (Seasonality) rõ rệt của sản phẩm.

### 🚀 Khuyến nghị giải pháp kinh doanh (Business Recommendations)
* **Tập trung nguồn lực Marketing:** Đẩy mạnh ngân sách quảng cáo cho dòng sản phẩm **Bikes** tại hai thị trường cốt lõi là Mỹ và Úc để tối đa hóa biên độ lợi nhuận.
* **Chiến lược giá cho Accessories & Clothing:** Cần xem xét lại cấu trúc chi phí và giá bán của nhóm hàng Phụ kiện và Quần áo tại thị trường Mỹ và các nước châu Âu, vì nhóm này có lượng đơn hàng lưu thông khá tốt nhưng biên lợi nhuận thu về hiện tại đang quá thấp.
* **Quản trị kho vận theo mùa:** Dựa vào biểu đồ xu hướng tăng tốc mạnh vào các tháng cuối năm, doanh nghiệp cần chủ động chuẩn bị nguồn cung và tăng lượng hàng tồn kho dự trữ từ cuối quý 2 để tránh tình trạng đứt gãy chuỗi cung ứng vào mùa cao điểm.
