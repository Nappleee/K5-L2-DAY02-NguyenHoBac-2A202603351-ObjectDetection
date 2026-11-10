# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `2A202603351_NguyenHoBac.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên: Nguyễn Hồ Bắc
- MSSV: 2A202603351
- Email: 26ai.bacnh@vinuni.edu.vn
- Lớp: L2B
- Link repo bài làm: https://github.com/Nappleee/K5-L2-DAY02-NguyenHoBac-2A202603351-ObjectDetection/tree/main
- Link Colab đã chạy:

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md](../../GUIDELINE_MINI.md). Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train: 50 
- Kết quả checker và lỗi đã xử lý: ĐẠT cấu trúc: 50/50 file nhãn hợp lệ. Chờ ground truth để chấm chất lượng.
- Danh sách ít nhất 10 ảnh đã rà bằng mắt: 1 -> 10 
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa: Thêm nhiều box thừa khi những hình ảnh quá mờ nhưng vẫn gán nhãn 
- Commit khóa nhãn ban đầu: 629032e69d71d588219f0d4200419f2a1bfb2738

## 4. Gold QC và rework

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP |448 | 441 | 
| FP |795| 531 |
| FN |205| 212 |
| Precision |0.3604 | 0.4537 |
| Recall |0.6861 | 0.6753
| F1 |0.4726 |  0.5428 |
| mean_iou_of_matches |0.7513 | 0.7508 |
| passed |false | false |

Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch: Python-3.13.18, GPU T4, Ultralytics 8.4.208, torch-2.14.1
- Các tham số thay đổi so với notebook nếu có và lý do: không
- Đường dẫn best checkpoint trong phiên chạy:  /content/Day2-Lab/outputs/yolo26_runs/vehicle_annotation/weights/best.pt

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision | 0.44689720463060395 |
| Recall | 0.249937455512707 |
| mAP50 | 0.273517869096708 |
| mAP50–95 | 0.1745195733032867 |

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa? lớp có recall thấp nhất là bus 
2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box? car 
3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét?  truck / van, Một số xe tải nhỏ có hình dáng gần giống cargo van
4. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì? Không sử dụng 10 ảnh eval để train vì mục đích của tập eval là đánh giá khả năng nhận diện của mô hình trên những dữ liệu mà mô hình chưa được học. Sử dụng ảnh eval làm dữ liệu đầu vào cho mô hình.

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
| | | | |

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Không tự nhận hoàn thành bước chưa chạy.

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.
