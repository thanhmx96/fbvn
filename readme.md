## Laravel PHP Framework

[![Build Status](https://travis-ci.org/laravel/framework.svg)](https://travis-ci.org/laravel/framework)
[![Total Downloads](https://poser.pugx.org/laravel/framework/downloads.svg)](https://packagist.org/packages/laravel/framework)
[![Latest Stable Version](https://poser.pugx.org/laravel/framework/v/stable.svg)](https://packagist.org/packages/laravel/framework)
[![Latest Unstable Version](https://poser.pugx.org/laravel/framework/v/unstable.svg)](https://packagist.org/packages/laravel/framework)
[![License](https://poser.pugx.org/laravel/framework/license.svg)](https://packagist.org/packages/laravel/framework)

# Git flow :

Đầu tiên các bạn fork về repo của mình, sau đó làm như sau

Click vào fork repo tại trang https://github.com/technical-dev/fbvn

Vào thư mục /www tại máy của bạn
Thao tác:

```
git clone https://github.com/taikhoancuaban/fbvn.git
git remote add fbvn https://github.com/technical-dev/fbvn.git
```

Sau khi clone về các bạn tạo branch develop:

```git checkout -b develop```

Và pull code từ develop của repo fbvn về

```git pull fbvn develop```

Mỗi task đều phải tạo 1 branch mới (không code trên develop) ví dụ làm phần layout:

```git checkout -b layout``` --> tạo branch layout

```git rebase develop``` --> đồng bộ code hiện tại với code từ repo develop

Khi làm cần phải checkout sang develop và pull code từ develop của repo fbvn xem có bị thay đổi gì hay không, nếu có thì tiếp tục rebase và xử lý conflict sau đó push lên repo của mình

Gửi pull request:

Sau khi làm 1 task giả sử làm xong task layout:
Add toàn bộ file đang làm vào staged

```git add .```

Commit 

```git commit -m "Nội dung comment"`` 

Sau đó push code lên repo của bạn (không push lên fbvn nhé)

```git push origin abc``` với abc là branch của task đang làm

Ở đây ví dụ bạn làm phần layout > thực hiện:

```git push origin layout```

Sau đó gửi pull request lên branch develop của fbvn để so sánh và merge (cần đọc document của git)

Lưu ý: Chỉ được gửi **1 commit / 1 pull request**

Updating...

# [Coding Standards](/docs/codingstandard.md)

# [Setup Environment](/docs/setup.md)
