
| **Story** | **AC#** | **Loại (Happy/Negative/Edge/Ràng buộc nghiệp vụ)** | **Given**                                        | **When**                                                | **Then**                                                                                                                                                                                             |
| --------------- | ------------- | ------------------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1               | AC  - 01     | Happy                                                         | Sách trong hệ thống vẫn chưa mượn               | Người dùng nhấn mượn một cuốn sách đó             | Hệ thống sẽ phản hồi "mượn sách thành công" And cập nhật trạng thái cuốn sách là "đã mượn" và gửi thông báo email đến người dùng với hạn đến nhận sách trong 48 giờ |
| 1               | AC - 02       | Negative                                                      | Sách trong hệ thống đã bị ai mượn trước đó | Người dùng nhấn mượn cuốn sách đó                   | Hệ thống sẽ thống báo lỗi cho người dùng là "cuốn sách này đã được mượn"                                                                                                               |
| 1               | AC - 03       | Edge                                                          | Chưa chọn sách để mượn                          | Người dùng nhấn mượn cuốn sách                        | Hệ thống thống báo "Chưa có cuốn sách nào được mượn" cùng với báo đỏ ở phần cuốn sách cần mượn                                                                                   |
| 2               | AC - 04       | Happy                                                         | Độc giả đã bật quyền nhận thống báo         | Hệ thống tiến hành gửi thông báo sách đã sẵn sàng | Hệ thống sẽ thống báo "đã có sách ở tiệm này" And sẽ để thông báo qua email                                                                                                              |
| 2               | AC - 05       | Negative                                                      | Độc giả đã tắt quyền nhận thống báo          | Hệ thống tiến hành gửi thông báo sách đã sẵn sàng | Hệ thống vẫn ghi nhận trạng thái gửi thành công qua email và hiển thị lịch sử thông báo qua mục "mục thư" trên tài khoản của độc giả                                             |
| 3               | AC - 06       | Rằng buộc nghiệp vụ                                       | Nhiều sách đang chưa được mượn                | Người dùng đặt nhiều sách cùng một lúc              | Hệ thống sẽ thông báo "Không thể lấy nhiều hơn 5 cuốn sách vui lòng trả bớt sách trước khi mượn thêm"                                                                                |
| 3               | AC - 07       | Happy                                                         | Cuốn sách được đặt chưa có ai mượn          | Người dùng mượn chỉ có 1 cuốn sách                  | Hệ thống sẽ thống báo "Mượn sách thành công" And yêu cầu người dùng đến thư viện để lấy sách trong thời gian có hạn                                                              |

+ Câu hỏi cần làm rõ:
+ | US | Câu hỏi                                                                                                                                                             |
  | -- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
  | 1  | Thời gian giữ chỗ 48 giờ này được tính bắt đầu từ thời điểm nào ?                                                                                    |
  | 2  | Nếu sau 48 giờ mà độc giả không đến nhận sách thì hệ thống sẽ tự động hủy phiếu mượn và đưa về trạng thái "chưa mượn" đúng không ?  |
  | 3  | Giới hạn số lượng độc giả có thể mượn được là 5 cuốn thì con số giới hạn này có phải cho tất cả hoặc sẽ phân chia theo mức hạng thẻ ? |
+ DoD

| STT | Nội dung                                                                                                                |
| --- | ------------------------------------------------------------------------------------------------------------------------ |
| 1   | Toàn bộ đoạn code sẽ được đẩy lên Git và phải được Code Review bởi ít nhất 1 lập trình viên        |
| 2   | Phải kiểm thử 100% các Unit Test cho nghiệp vụ chính, không có lỗi nghiêm trọng                              |
| 3   | Giao diện hiển thị đúng theo thiết kế, bảo đảm tương thích tốt trên cả Điện thoại và Máy tính      |
| 4   | Cập nhật tài liệu hướng dẫn sử dụng cho thủ thư và độc giả                                                |
| 5   | Tính năng được deploy thành công trên môi trường Test và được Product Owner đạt yêu cầu nghiệm thu  |

+ Story 1 này chưa coi là Done:
+ Vì: mặc dù đủ AC cho User Story đó nhưng chưa đạt được tiêu chí nghiệm thu của DoD là kiểm thử và việc US đạt AC nhưng chưa qua kiểm định kỹ quy trình sẽ không thể đảm bảo được chất lượng cho hệ thống
