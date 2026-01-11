# GAME DESIGN DOCUMENT (GDD)

## 1. Thông tin chung

**Tên game:** Save The Pets
**Thể loại:** Puzzle / Draw Line
**Nền tảng:** Mobile (Android / iOS)
**Engine:** Unity 6000
**Camera:** 2D – Orthographic
**Đối tượng người chơi:** Casual – mọi lứa tuổi
**Phong cách:** Dễ thương, vui nhộn

---

## 2. Tổng quan gameplay

Save The Pets là game puzzle vẽ đường (draw line). Người chơi vẽ các đường để **bảo vệ chú chó** khỏi các **con ong bay ra từ tổ**.

Sau khi người chơi **vẽ line xong**, game bắt đầu chạy timer:

* Nếu **chú chó được bảo vệ an toàn trong 6 giây** → **WIN**
* Nếu **chú chó bị ong đốt** trong thời gian này → **LOSE**

---

## 3. Cơ chế chơi chính

### 3.1 Điều khiển

* **Vuốt / vẽ line trên màn hình** để tạo vật cản
* **Mỗi level CHỈ ĐƯỢC VẼ 1 LẦN DUY NHẤT**
* Người chơi phải tính toán chính xác trước khi thả tay
* Không được vẽ thêm sau khi bắt đầu chạy timer

### 3.2 Line bảo vệ

* Line được xem là vật thể vật lý
* Ong va chạm line sẽ bị chặn / đổi hướng
* Line cố định sau khi người chơi hoàn thành việc vẽ

### 3.3 Con chó (Pet)

* Đứng yên tại vị trí cố định
* Có animation:

  * Idle
  * Hoảng sợ khi ong tới gần
  * Vui mừng khi thắng

### 3.4 Ong

* Sau khi vẽ line xong, ong sẽ **bay ra từ tổ**
* Di chuyển theo AI đơn giản:

  * Bay về phía chú chó
  * Bị ảnh hưởng bởi va chạm vật lý

---

## 4. Điều kiện thắng / thua

### Thắng (Win)

* Người chơi vẽ line xong
* Bảo vệ được chú chó **trong 6 giây liên tục**

### Thua (Lose)

* Trong 6 giây:

  * Ong chạm vào chú chó
  * Chó bị đốt (trigger animation / effect)

---

## 5. Cấu trúc Scene

### 5.1 Load Scene

* Logo game
* Thanh loading
* Khởi tạo:

  * AdMob
  * Audio Manager
  * Save Data

### 5.2 Home Scene

* Button:

  * Play
  * Select Level
  * Theme
  * Setting
* Hiển thị:

  * Số kim cương

### 5.3 Gameplay Scene

* Khu vực vẽ line
* Con chó
* Tổ ong
* UI:

  * Timer 6 giây
  * Button Reset

---

## 6. Hệ thống Popup

### 6.1 PopupSetting

* Bật / tắt:

  * Nhạc nền
  * Âm thanh
  * Rung

### 6.2 PopupTheme

* Mua theme bằng kim cương:

  * Background
  * Skin chó
  * Skin ong

### 6.3 PopupSelectLevel

* Chọn level đã mở khóa

### 6.4 PopupWin

* Hiển thị kim cương nhận được
* Button:

  * Xem quảng cáo → **x2 kim cương**
  * Next Level

### 6.5 PopupLose

* Button:

  * Retry
  * Home

---

## 7. Tiền tệ trong game

### 7.1 Kim cương (Diamond)

* Nhận từ:

  * Thắng level
  * Xem quảng cáo
* Dùng để:

  * Mua skin / theme

---

## 8. Monetization

### 8.1 Quảng cáo (AdMob)

* **Rewarded Ads**:

  * x2 kim cương sau khi thắng

* **Interstitial Ads**:

  * Hiển thị sau X level

---

## 9. Âm thanh & hiệu ứng

### 9.1 Sound Effect (SFX)

* Vẽ line
* Ong bay
* Ong đốt
* Thắng / Thua
* Click UI

### 9.2 Nhạc nền (BGM)

* Home: nhẹ nhàng, vui vẻ
* Gameplay: căng thẳng nhẹ

---

## 10. Level Design

* Level tăng dần độ khó:

  * Nhiều ong hơn
  * Tốc độ ong nhanh hơn
  * Địa hình phức tạp hơn
* Có bẫy:

  * Gió
  * Tường
  * Vật thể động

---

## 11. Lưu trữ dữ liệu

* Save:

  * Level đã mở
  * Kim cương
  * Theme đã mua

---

## 12. Mục tiêu thiết kế

* Luật chơi hiểu trong 3 giây
* Dễ chơi – gây nghiện
* Phù hợp thị trường puzzle
* Tối ưu quảng cáo nhưng không phá trải nghiệm

---

**End of GDD – Save The Pets**
