```bash
git init
git status
git add
# revert all changed on the filename -> last commit
git restore filename
# make commit with message
git commit -m "Ghi chú về commit"
# if do not push commit to remote repository
# then you can make commit with new message -> replace last commit
git commit --amend -m "Thông tin về commit"

# show log
git log
# show online
git log --oneline

# git reset with param --soft
# Trường hợp này sẽ hủy commit cuối, con trỏ HEAD sẽ chuyển về commit cha. Đồng thời những thay đổi của commit cuối được chuyển vào vùng staging nhằm để có cơ hội commit lại hoặc sửa đổi, cú pháp lệnh như sau:
git reset --soft HEAD~1

# git reset with param --hard
# Khi dùng tham số --hard thì kết quả giống với dùng tham số --soft, chỉ có một khác biết là nội dung thay đổi của commit cuối không đưa đưa vào staging mà bị hủy luôn. Trường hợp này dùng khi bạn quyết định hủy hoàn toàn commit cuối
git reset --hard HEAD~1

# Hủy git add
# Nếu bạn đã dùng lệnh git add để cập nhật thay đổi vào vùng staging, bạn có thể hủy thao tác này bằng cách thực hiện lệnh:
git reset

# Hủy đưa một file vào staging
# Nếu muốn hủy một file nào đó trong vùng staging chứ không phải toàn bộ thì dùng lệnh
git reset -- filename

# Khi có sự thay đổi của thư mục làm việc mà chưa chỉ mục, thì có thể xem sự thay đổi của nó với commit cuối
git diff

# Kiểm tra sự thay đổi của index (staging) với commit cuối
git diff --staged

# Kiểm tra thay đổi giữa hai commit
git diff hash-commit1 hash-commit2
# Kiểm tra sự thay đổi của hai nhánh
git diff branch1 branch2

git checkout master
# Giả sử có file index.html, muốn phục hồi nó về phiên bản ở commit có mã hash là HASH, thì thực hiện:
git checkout HASH index.html
# Nếu bạn muốn phục hồi nội dung từ index (staging nếu có, nếu không từ commit cuối) thì đơn giản là
git checkout index.html
# Phục hồi nhiều file, ví dụ *.html từ index (staging nếu có, nếu không từ commit cuối)
git checkout -- *.html
# Thì lúc này con trỏ HEAD sẽ chuyển đến commit này, và Git ở chế độ head detached, bạn làm việc trên một nhánh tạm thời
# Nếu có thực hiện các commit trên nhánh này và cần lưu lại thì cuối cùng tạo nhánh mới bằng lệnh

# git merger VS git rebase
# https://xuanthulab.net/lenh-git-merge-va-rebase-gop-va-viet-lai-lich-su-commit.html
```