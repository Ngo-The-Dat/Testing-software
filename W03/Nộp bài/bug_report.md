## **Bug ID**: FR03-bug-01

**Mô tả**: Màn hình Quên mật khẩu (Bước 1/2) thiếu chỉ báo bước (Step Indicator) "Bước 1 / 2" và thiếu nút/liên kết "Quay lại đăng nhập" như đặc tả yêu cầu.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR03-bug-01.png>)

---

## **Bug ID**: FR03-bug-02

**Mô tả**: 

1. Giao diện Đặt lại mật khẩu (Bước 2/2) không có trường "Xác nhận mật khẩu mới" (Confirm New Password), không thể kiểm tra hai trường mật khẩu khớp nhau như đặc tả yêu cầu. 

2. Mã OTP được hệ thống tạo ra chỉ có **4 chữ số** thay vì **6 chữ số** như yêu cầu trong đặc tả FR-03.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR03-bug-02.png>)

---

## **Bug ID**: FR03-bug-03

**Mô tả**: Màn hình Đặt lại mật khẩu (Bước 2/2) sử dụng biểu thức chính quy (Regex) kiểm tra mật khẩu mạnh bị sai logic (tương tự như màn hình Đăng ký FR-01). Lỗi này bắt buộc mật khẩu mới phải chứa khoảng trắng (space) và chặn toàn bộ các ký tự đặc biệt hợp lệ (ví dụ: `!`, `@`, `#`, `$`, `%`, `*`...). Do đó, người dùng nhập mật khẩu mạnh chuẩn sẽ bị báo lỗi "Mật khẩu quá yếu!", trong khi nhập mật khẩu chứa dấu cách lại được chấp nhận.
**Screenshot GitHub Issues page**:

![\[cái này tôi sẽ tự dán vào\]](<bug images/FR03-bug-03.png>)

---

## **Bug ID**: FR10-bug-01

**Mô tả**: API Admin cập nhật trạng thái đơn hàng (`PUT /api/admin/orders/:id/status`) không kiểm tra quyền admin (`role === 'admin'`). Người dùng có tài khoản thông thường (role = 'user') vẫn có thể gọi API này để thay đổi trạng thái của bất kỳ đơn hàng nào trong hệ thống.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR10-bug-01.png>)

---

## **Bug ID**: FR10-bug-02

**Mô tả**: Người dùng có thể tự hủy đơn hàng khi đơn hàng đang ở trạng thái "Đang giao" (`shipping`) hoặc các trạng thái không hợp lệ khác (như `draft`). Theo đặc tả FR-10: "Khi đơn hàng đã ở trạng thái shipping, User không được phép tự hủy — chỉ Admin mới có thể thao tác". Giao diện người dùng cũng hiển thị sai nút "Hủy đơn" đối với đơn hàng ở trạng thái "Đang giao".

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR10-bug-02.png>)

---

## **Bug ID**: FR10-bug-03

**Mô tả**: API Admin cập nhật trạng thái đơn hàng cho phép chuyển đổi từ trạng thái kết thúc `canceled` sang trạng thái kết thúc khác `delivered`. Theo đặc tả FR-10: "Trạng thái `delivered` và `canceled` là trạng thái kết thúc — không được phép chuyển sang bất kỳ trạng thái nào khác."

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR10-bug-03.png>)

---

## **Bug ID**: FR16-bug-01

**Mô tả**: Giao diện không xử lý đúng chuẩn RFC 4180 khi phân tích cú pháp file CSV có chứa dấu phẩy được bọc trong dấu nháy kép. Hệ thống sử dụng phương thức `split(",")` đơn giản trên client để chia các trường, dẫn đến việc các trường chứa dấu phẩy bị phân tách thành nhiều cột khác nhau, gây lệch cột (column shifting) dữ liệu nghiêm trọng khi gửi lên API.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR16-bug-01.png>)

---

## **Bug ID**: FR16-bug-02

**Mô tả**: Giao diện không thực hiện kiểm tra định dạng và phần mở rộng (đuôi file) của file tải lên. Hệ thống cho phép người dùng chọn và tiến hành import các file không phải CSV (ví dụ: file bảng tính `.xlsx`, file văn bản hoặc file không có phần mở rộng). Khi tải lên file sai định dạng, `FileReader` trên frontend vẫn cố đọc nội dung file dưới dạng text và gửi dữ liệu lỗi lên API.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR16-bug-02.png>)

---

## **Bug ID**: FR16-bug-03

**Mô tả**: Giao diện không kiểm tra cấu trúc dòng header đầu tiên của file CSV. Khi file CSV có dòng header sai tên cột hoặc thiếu các cột bắt buộc (`name`, `price`), hệ thống không từ chối file hay hiển thị lỗi cấu trúc file không hợp lệ. Thay vào đó, hệ thống vẫn tiếp tục xử lý, tự động ánh xạ (map) các trường không chuẩn hoặc gửi lên API dẫn đến báo lỗi không đúng bản chất của cấu trúc file.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR16-bug-03.png>)

---

## **Bug ID**: FR16-bug-04

**Mô tả**: Hệ thống không kiểm tra giới hạn độ dài của tên sản phẩm (tối đa 255 ký tự theo ràng buộc FR-15) khi thực hiện import sản phẩm từ file CSV. Khi người dùng tải lên sản phẩm có tên dài vượt quá 255 ký tự (Ví dụ: 256 ký tự), hệ thống vẫn chấp nhận và lưu thành công sản phẩm đó vào cơ sở dữ liệu.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR16-bug-04.png>)

---

## **Bug ID**: FR16-bug-05

**Mô tả**: Hệ thống hoàn toàn thiếu validation cho thuộc tính giá sản phẩm (`price`) khi import từ CSV (yêu cầu là số dương > 0). Hệ thống cho phép import thành công các sản phẩm có giá bằng 0, giá trị âm (Ví dụ: `-50000`, `-1`), giá trị không phải là số (Ví dụ: `abc`), hoặc tự động chuyển đổi thành 0 khi để trống giá tiền và import thành công.

**Screenshot GitHub Issues page**:
![alt text](FR16-bug-05.png)
---

## **Bug ID**: FR16-bug-06

**Mô tả**: Hệ thống không kiểm tra tính hợp lệ và sự tồn tại của danh mục sản phẩm (`category_id`) khi thực hiện import từ CSV. Hệ thống chấp nhận và lưu thành công các sản phẩm có ID danh mục không tồn tại trong hệ thống (Ví dụ: `9999`), ID danh mục không phải số nguyên (Ví dụ: `abc`), hoặc tự động gán danh mục mặc định = `1` khi người dùng để trống ID danh mục và tiến hành import thành công.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR16-bug-06.png>)

---

## **Bug ID**: FR16-bug-07

**Mô tả**: Hệ thống không thực hiện cơ chế Transaction (giao dịch nguyên tử — All-or-Nothing Rollback). Theo đặc tả FR-16: "Nếu có lỗi ở bất kỳ dòng nào, toàn bộ import phải được rollback". Tuy nhiên, backend API thực hiện chèn dữ liệu từng dòng độc lập mà không sử dụng giao dịch (Transaction) trong SQLite. Do đó, khi trong file CSV chứa cả hàng hợp lệ và hàng lỗi, hệ thống vẫn lưu các dòng hợp lệ vào cơ sở dữ liệu thay vì rollback toàn bộ.

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR16-bug-07.png>)

---

## **Bug ID**: FR20-bug-01

**Mô tả**: API backend hủy đơn hàng (`PUT /api/orders/:id/cancel`) không kiểm tra và chặn trường hợp đơn hàng đang ở trạng thái "Đang giao" (`shipping`). Người dùng vẫn có thể gửi yêu cầu hủy trực tiếp đến API để chuyển đổi trạng thái đơn hàng đang đi giao thành "Đã hủy" (`canceled`), vi phạm đặc tả của sơ đồ chuyển đổi trạng thái đơn hàng (State Machine).

**Screenshot GitHub Issues page**:
![alt text](<bug images/FR20-bug-01.png>)