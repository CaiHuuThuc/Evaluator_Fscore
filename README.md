# Evaluator_Fscore

- Script đánh giá điểm Fscore cho Named Entity Recognition - POS tagging.

- Có 3 kiểu đánh giá:
  - Strict matching: cần dự đoán đúng tất cả token trong một entity mới tính là đúng entity đó.
  - Relax matching: chỉ cần dự đoán đúng 1 phần token trong 1 entity thì được tính là đúng entity đó.
  - Token matching: xem một token là một entity.

# Cách sử dụng
Yêu cầu:
  
  - File gold và guess tách biệt nhau
  
  - Định dạng file theo format: mỗi dòng là 1 token từ câu, dạng word<tab>label, mỗi câu cách nhau bằng dòng trắng.
  
usage: my_evaluate.py [-h] [--gold-fn GOLD_FN] [--gold-header]
                      [--guess-fn GUESS_FN] [--guess-header] [-s] [-r] [-t]

Đánh giá kết quả mô hình

optional arguments:
  -h, --help            show this help message and exit
  --gold-fn GOLD_FN     Đường dẫn đến gold file
  --gold-header         True nếu file gold data có header, false nếu không
                        (Mặc định: False)
  --guess-fn GUESS_FN   Đường dẫn đến guess file
  --guess-header        True nếu file guess data có header, false nếu không
                        (Mặc định: False)
  -s, --strict, --strict-matching
                        Đánh giá bằng strict matching (Mặc định: False)
  -r, --relax, --relax-matching
                        Đánh giá bằng relax matching (Mặc định: False)
  -t, --token, --token-matching
                        Đánh giá bằng token matching (Mặc định: False)

Nếu không kiểu đánh giá nào được chọn, mặc định strict matching sẽ được chọn
