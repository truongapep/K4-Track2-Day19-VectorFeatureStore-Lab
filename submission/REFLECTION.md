# Reflection — Lab 19

**Tên:** Nguyễn Xuân Trường  
**Cohort:** A20-K4  
**Path đã chạy:** lite (Ubuntu)

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

Trên golden set 50 queries, hybrid đạt Precision@10 trung bình 78,6%, nhỉnh
hơn BM25 (77,8%) và semantic (73,2%). Hybrid thắng rõ ở `mixed` (100%, so với
97,0% BM25 và 98,5% semantic). Ở `exact`, BM25 và hybrid hòa nhau (96,7%);
ở `paraphrase`, cấu hình hiện tại cho semantic 24,0%, hybrid 32,0% và BM25
33,3%. Vì vậy vector chưa thắng trên paraphrase trong phép đo này; mô hình
bge-small-en có thể là nguyên nhân trên câu tiếng Việt và cần được đánh giá
lại với embedding đa ngữ trước khi kết luận. Không cần hybrid khi truy vấn là
mã/tên chính xác và BM25 đã đủ nhanh, hoặc khi một mô hình vector đa ngữ đã
được kiểm chứng cho tác vụ paraphrase: hybrid tăng chi phí/độ trễ mà không
đảm bảo cải thiện.

---

## Điều ngạc nhiên nhất khi làm lab này

Post-filter chỉ giữ recall 0,00 ở filter chọn lọc 3,8%, trong khi filtered-ANN
giữ 1,00; lấy 50% corpus mới đưa over-fetch recall về 1,00.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: —
