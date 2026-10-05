# Reflection — Lab 19

**Tên:** Hồ Thái Hòa
**Cohort:** _<A20-K4>_
**Path đã chạy:** lite

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

Theo thiết kế của lab, BM25 thường phù hợp nhất với `exact` vì bắt được từ khóa và thuật ngữ trùng khớp. Vector search có lợi thế với `paraphrase` vì tìm theo ý nghĩa thay vì yêu cầu cùng cách diễn đạt; tuy nhiên, embedding mặc định thiên về tiếng Anh nên chất lượng tiếng Việt có thể hạn chế. Với `mixed`, hybrid kết hợp tín hiệu từ khóa và ngữ nghĩa, nên thường ổn định hơn; cần đối chiếu bảng Precision@10 đã chạy để xác nhận kết quả thực tế. Tôi sẽ chọn BM25 khi truy vấn chứa mã định danh hoặc thuật ngữ chính xác, và chọn vector khi truy vấn diễn đạt linh hoạt nhưng embedding phù hợp ngôn ngữ. Hybrid không cần thiết nếu một phương thức đơn lẻ đã đạt chất lượng yêu cầu và độ trễ hoặc chi phí bổ sung không đáng.

---

## Điều ngạc nhiên nhất khi làm lab này

Điểm đáng chú ý là chọn embedding model ảnh hưởng trực tiếp đến khả năng tìm kiếm paraphrase tiếng Việt. Tăng kích thước vector không tự động cải thiện kết quả nếu model không phù hợp với ngôn ngữ và corpus.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
