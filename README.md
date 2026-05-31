# Local AI Chat — Web UI

Chatbot web với sidebar lịch sử, dùng LM Studio làm backend AI.

## Yêu cầu

- Python 3.9+
- LM Studio đang chạy với Local Server bật (mặc định port 1234)

## Cài đặt

```bash
cd chatbot
pip install -r requirements.txt
```

## Chạy

1. Mở LM Studio → vào tab **Local Server** → bấm **Start Server**
2. Load một model bất kỳ trong LM Studio
3. Chạy Flask:

```bash
python app.py
```

4. Mở trình duyệt: http://localhost:5000

## Cấu trúc project

```
chatbot/
├── app.py              ← Flask backend
├── requirements.txt
└── templates/
    └── index.html      ← Toàn bộ UI
```

## Tùy chỉnh

- **Port LM Studio**: Đổi `localhost:1234` trong `app.py` nếu dùng port khác
- **Temperature**: Chỉnh `temperature=0.7` trong hàm `generate()` (0 = chính xác, 1 = sáng tạo)
- **Max tokens**: Chỉnh `max_tokens=2048`

## Lưu ý

Lịch sử hội thoại lưu trong RAM — sẽ mất khi restart server.
Muốn lưu vĩnh viễn thì thêm SQLite sau.
