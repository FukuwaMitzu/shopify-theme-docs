---
title: Templates & Metafields
---

# Templates & Metafields

<div class="video-wrapper">
    <iframe width="100%" height="100%" src="https://www.youtube.com/embed/5yxu9P4DE2g?si=NYG9E7jWz4kcg-IN" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="true"></iframe>
</div>

## Templates

Templates là bộ sưu tập các sections được cấu hình để mang đến giao diện nhất quán cho cửa hàng trực tuyến của bạn. Những sections nào có sẵn trong template sẽ phụ thuộc vào chức năng theme của bạn. Trong theme editor, bạn có thể tìm hiểu xem nên áp dụng mẫu nào cho trang nào, rồi chỉnh sửa thông tin cho phù hợp với khách hàng của mình.

Khi chỉnh sửa template, tất cả các trang sử dụng template nào thì giao diện trang đó sẽ thay đổi theo template tương ứng. Ví dụ như, nếu bạn thêm form newsletter signup cho một collection template, tất cả các collections pages truớc đó sử dụng default collection template thì giờ đây sẽ hiển thị thêm một form newsletter signup.

:::note
Bạn có thể sở hữu tổng cộng tối đa **1000** templates.
:::

### Khởi tạo template

Có một số loại template có thể được sử dụng để hiển thị cho nhiều trang trong cửa hàng của bạn. Những loại kể đến bao gồm:

+ collections
+ products
+ blogs
+ blog posts
+ pages

Tất cả các theme đều cung cấp các default template cho mỗi loại page. Đây là template mặc định trong trường hợp bạn chưa thiết lập template thay thế cho các page tương ứng.

Bất cứ thay đổi nào ở template sẽ ảnh hưởng đến tất các các page dùng chung template đó. Để thay đổi giao diện của template đối với các trang đặc biệt, bạn có thể tạo một template mới kế thừa các tính năng và giao diện của template trước đó hoặc một template bất kì nào khác. 

Các bước tạo theme:

1. Từ giao diện Shopify admin, đi đến `Online Store > Themes`.

![Shopify Basic](/img/shopify_theme_config.png)

2. Tìm theme mà bạn muốn edit, sau đó click chọn `Customize`.
3. Sử dụng drop-down menu để chọn một template. Sau đó chọn `Create template`.

![Shopify Basic](/img/shopify_theme_dropdown.png)

![Shopify Basic](/img/create_template.png)

4. Đặt tên cho template của bạn.
5. Tại mục `Based on`, lựa chọn template có trong store của bạn để template mới này kế thừa các giao diện và tính năng.

![Shopify Basic](/img/template_based_on.png)

6. Click chọn `Create template`.

### Áp dụng template cho product page

Các bước áp dụng template cho product page:

1. Từ giao diện Shopify admin, đi đến `Products`.

2. Chọn sản phẩm cần edit.

3. Chọn template tại mục `Theme template`.

![Shopify Basic](/img/theme_template.png)

## Metafields

Metafields giúp bạn tùy biến các chức năng và hiển thị của Shopify store hoặc để quản trị nội bộ. Thông tin của metafields có thể được hiển thị trên storefront thông qua nhiều cách. Ví dụ, một nhà cung cấp nến muốn hiển thị thời gian cháy của ngọn nến ở trên product page, hay một cửa hàng tạp hóa muốn hiển thị ngày hết hạn của các sản phẩm. Ngoài ra còn có các thông tin khác như:

+ color swatches
+ thời gian phát hành (launch dates)
+ sản phẩm liên quan (related products)
+ tóm tắt bài viết (blog post summaries)
+ thông tin file tải về (files for download)
+ công thức (lists of ingredients)

Bạn có thể thêm metafields cho các products, collections, customers, orders và các thành phần khác trong store của bạn, trực tiếp thông qua giao diện Shopify admin.

### Khởi tạo một metafield

1. Từ giao diện home của Shopify admin, đi đến `Settings > Custom data`.
2. Tại mục `Metafields`, click chọn `Product`. 

![Metafields](/img/custom-data-metafield-01.png)

3. Click chọn `Add definition`.
4. Thiết lập tên và các cài đặt cần thiết cho metafield của bạn.
5. Click `Save`. 

Sau khi đã tạo xong một metafield, ta có thể bắt đầu [thiết lập giá trị cho chúng](#thêm-giá-trị-cho-metafield).

### Thêm giá trị cho metafield

Sau khi [khởi tạo metafield](#khởi-tạo-một-metafield), bạn có thể gán giá trị cho các page tương ứng ở Shopify admin. Ví dụ, nếu như bạn đã khởi tạo một metafield đại diện cho hạn sử dụng của một sản phẩm, bạn sẽ phải bổ sung thông tin hạn sử dụng chi tiết cho từng sản phẩm trên Shopify admin thông qua metafield đó. Bằng cách thêm các giá trị cho các metafield, bạn sẽ lưu thêm được một số các thông tin đặc biệt phục vụ cho quá trình theo dõi và hiển thị thông tin ngoài storefront.

Những metafield nào mà được pinned thì sẽ hiển thị đưới dạng bảng editable trên Shopify admin theo thứ tự mà chúng hiển thị ở danh sách khao báo metafield của bạn. Bạn có thể click từng dòng để hiển thị kiểu dữ liệu và thông tin chi tiết của metafield, và nhập giá trị nếu cần.

![Pinned indication](/img/pinned-indication.png)