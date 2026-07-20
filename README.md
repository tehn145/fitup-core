# 🏋️‍♂️ FitUp — Giải pháp Fitness toàn diện

**Đồ án môn học:** NT118.Q13 — Phát triển ứng dụng trên thiết bị di động
**Giảng viên hướng dẫn:** Trần Hồng Nghi
**Nhóm 8**

---

## 📝 Giới thiệu

FitUp là ứng dụng Android kết nối người tập luyện với huấn luyện viên (HLV), lấy cảm hứng từ các nền tảng fitness như FitTogether, My Workout Group, Arrow, Hevy. Ứng dụng hướng tới việc cá nhân hóa hành trình tập luyện thông qua matching thông minh, cộng đồng chia sẻ, và trợ lý AI.

## 💡 Tính năng chính

| Module | Mô tả |
|---|---|
| **Matching** | Phân tích hồ sơ sức khỏe, mục tiêu, vị trí để đề xuất HLV phù hợp qua engine matching riêng (`AIMatchEngine`) |
| **Discovery** | Cộng đồng tập luyện: đăng bài, bình luận, follow/following, tìm kiếm người dùng |
| **Profile** | Quản lý thông tin cá nhân, chỉ số cơ thể, mục tiêu, cấp độ thể lực |
| **Message** | Nhắn tin real-time, đặt lịch buổi tập, đánh giá sau buổi tập với HLV |
| **Home** | Danh sách HLV nổi bật, gợi ý HLV gần vị trí (Mapbox), bài tập theo danh mục |
| **AI Assistant** | Chat hỏi đáp kiến thức fitness, quiz sức khỏe hằng ngày, tích hợp Groq API & Gemini API |

## 🏗️ Kiến trúc & Tech Stack

- **Ngôn ngữ:** Java (Android SDK, minSdk 24 / targetSdk & compileSdk 36)
- **Cấu trúc:** Package theo tính năng cho module Matching (`feature/match/{engine,model,ui,util}`), phần còn lại tổ chức theo Activity/Fragment truyền thống
- **Backend & dữ liệu:** Firebase (Authentication, Firestore, Realtime Database, Storage, Cloud Functions) qua `firebase-bom`
- **Networking:** Retrofit2 + Gson — gọi Groq API và Gemini API cho tính năng trợ lý AI
- **Bản đồ & vị trí:** Mapbox SDK, Google Play Services Location
- **UI hỗ trợ:** Glide (ảnh), CircleImageView, ViewPager2, RecyclerView, Firebase UI Storage
- **API key** (Groq) được inject qua `local.properties` + `BuildConfig`, không hard-code trong source — điểm cộng về security hygiene cơ bản

## 🚀 Cài đặt & chạy thử

```bash
git clone https://github.com/tehn145/fitup-core.git
cd fitup-core
# Thêm GROQ_API_KEY vào local.properties
# Thêm google-services.json vào thư mục app/
./gradlew assembleDebug
```

## 📸 Demo

*(Update in the future — nên bổ sung ảnh chụp màn hình hoặc video demo ngắn ở đây)*

## 👥 Thành viên nhóm gốc (đồ án NT118.Q13)

| Họ và tên | MSSV |
|---|---|
| Huỳnh Minh Hiếu | 23520477 |
| Ngô Kim Thành | 23521447 |
| Trần Bùi Nhật Nguyên | 23521059 |

## 🙋 Đóng góp cá nhân

*(Điền cụ thể phần bạn phụ trách, ví dụ:)*
- Thiết kế & phát triển module Matching (`AIMatchEngine`, `MatchProfile`, `MatchResult`)
- Tích hợp trợ lý AI (Groq API, Gemini API) cho tính năng chat & quiz sức khỏe
- Xây dựng lớp tích hợp Firebase (Auth, Firestore, Storage)

---

**Made by Group 8, NT118.Q13**
