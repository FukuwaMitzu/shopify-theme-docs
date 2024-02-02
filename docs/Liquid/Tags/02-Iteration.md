---
title: Iteration
---

# Iteration

Quá trình thực hiện một hành động lặp đi lặp lại với từng thành phần trong một tập hợp được gọi là một Iteration.
Trong Liquid, Iteration biểu diễn dưới dạng các câu lệnh sau:

## for

Lặp lại quá trình thực thi một khối lệnh. Để lấy thông tin về vòng lặp hiện tại, sử dụng [`forloop`](#forloop-object) (đây là object).

```liquid title="Input"
{% for product in collection.products %}
  {{ product.title }}
{% endfor %}
```

```html title="Output"
hat shirt pants
```

### else

Bổ trợ cho trường hợp vòng lặp có số lần lặp bằng 0.

```liquid title="Input"
{% for product in collection.products %}
  {{ product.title }}
{% else %}
  The collection is empty.
{% endfor %}
```

```html title="Output"
The collection is empty.
```

### break

Dùng để ngưng quá trình lặp.

```liquid title="Input"
{% for i in (1..5) %}
  {% if i == 4 %}
    {% break %}
  {% else %}
    {{ i }}
  {% endif %}
{% endfor %}
```

```html title="Output"
1 2 3
```

### continue

Dùng để skip vị trí vòng lặp hiện tại.

```liquid title="Input"
{% for i in (1..5) %}
  {% if i == 4 %}
    {% continue %}
  {% else %}
    {{ i }}
  {% endif %}
{% endfor %}
```

```html title="Output"
1 2 3 5
```

:::tip
Bạn cũng có thể gọi **key** và **value** trong vòng lặp bằng cách sử dụng dấu `[]` để truy cập key và value tương ứng.

```liquid title="Input"
{% for item in persons %}
  {{ item[0] }}: {{ item[1] }}
{% endfor %}
```

```html title="Output"
name: Jack age: 18 name: James age: 34
```

Ở ví dụ trên:

- `{{ item[0] }}` là key.
- `{{ item[1] }}` là value.
  :::

## for (parameters)

Các tham số vòng lặp được đặt sau biểu thức vòng lặp có dạng `foo:bar`, trong đó `foo` là từ khóa và `bar` là giá trị tham số.

### limit

Tham số cho phép giới hạn số lần cần lặp.

```liquid title="Input"
<!-- if array = [1,2,3,4,5,6] -->
{% for item in array limit:2 %}
  {{ item }}
{% endfor %}
```

```html title="Output"
1 2
```

### offset

Bắt đầu vị trí vòng lặp nhất định.

```liquid title="Input"
<!-- if array = [1,2,3,4,5,6] -->
{% for item in array offset:2 %}
  {{ item }}
{% endfor %}
```

```html title="Output"
3 4 5 6
```

:::tip
Bạn có thể tiếp tục lặp một danh sách tại vị trí dang dở của vòng lặp trước đó bằng cách sử dụng từ khóa `continue`.

```liquid title="Input"
<!-- if array = [1,2,3,4,5,6] -->
{% for item in array limit: 3 %}
  {{ item }}
{% endfor %}
{% for item in array limit: 3 offset: continue %}
  {{ item }}
{% endfor %}
```

```html title="Output"
1 2 3 4 5 6
```

:::

### range

Định nghĩa một khoảng dãy số cần lặp. Dãy số có thể được định nghĩa thông qua một biểu thức dãy số hoặc cũng có thể là một biến.

```liquid title="Input"
{% for i in (3..5) %}
  {{ i }}
{% endfor %}

{% assign num = 4 %}
{% assign range = (1..num) %}
{% for i in range %}
  {{ i }}
{% endfor %}
```

```html title="Output"
3 4 5 1 2 3 4
```

### reversed

Đảo ngược vị trí lặp.

```liquid title="Input"
<!-- if array = [1,2,3,4,5,6] -->
{% for item in array reversed %}
  {{ item }}
{% endfor %}
```

```html title="Output"
6 5 4 3 2 1
```

## forloop (object)

Cung cấp thông tin về vòng lặp hiện tại.

```json
{
  "first": true,
  "index": 1,
  "index0": 0,
  "last": false,
  "length": 4,
  "rindex": 3
}
```

### Sử dụng biến forloop

```liquid title="Input"
{% assign smoothie_flavors = "orange, strawberry, banana" | split: ", " %}

{% for flavor in smoothie_flavors -%}
  {%- if forloop.length > 0 -%}
    {{ flavor }}{% unless forloop.last %}-{% endunless -%}
  {%- endif -%}
{% endfor %}
```

```html title="Output"
orange-strawberry-banana
```

### Các thuộc tính của forloop

| Thuộc tính   | Mô tả                                                                                                         | Kiểu trả về |
| ------------ | ------------------------------------------------------------------------------------------------------------- | ----------- |
| `length`     | Tổng số lần cần lặp.                                                                                          | `number`    |
| `parentloop` | Giá trị forloop của vòng lặp cha . Nếu như vòng lặp hiện tại không nằm trong một vòng lặp khác sẽ trả về nil. | `forloop`   |
| `index`      | Vị trí hiện tại của vòng lặp với dãy tính từ 1.                                                               | `number`    |
| `index0`     | Vị trí hiện tại của vòng lặp với dãy tính từ 0.                                                               | `number`    |
| `rindex`     | Vị trí hiện tại của vòng lặp tính từ phải sang. Nhưng dãy tính từ 1.                                          | `number`    |
| `rindex0`    | Vị trí hiện tại của vòng lặp tính từ phải sang. Nhưng dãy tính từ 0.                                          | `number`    |
| `first`      | Trả về `true` nếu đang lặp ở vị trí đầu tiên. Ngược lại trả về `false`.                                       | `boolean`   |
| `last`       | Trả về `true` nếu đang ở vị trí cuối cùng. Ngược lại trả về `false`.                                          | `boolean`   |

## Cycle
