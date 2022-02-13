# 1. Overloading and Overriding 

##  `Overloading`
Overloading là một kĩ thuật cho phép trong cùng một class có thể có nhiều phương thức cùng tên nhưng khác nhau về số lượng tham số hoặc kiểu dữ liệu tham số. 

## `Overriding`
Overrding (tên đầy đủ là Method Overriding), được sử dụng trong trường hợp lớp con kế thừa từ lớp cha và muốn định nghĩa lại một phương thức đã có mặt ở lớp cha.

## Compaction
| Overloading                                                | Overriding                                             |
| ---------------------------------------------------------- | ------------------------------------------------------ |
| Thể hiện đa hình tại *compile time*                        | Thể hiện đa hình tại *runtime*                         |
| *Thêm hành vi* cho phương thức                             | *Thay đổi hành vi* hiện tại của phương thức            |
| Có thể *Khác nhau* về số lượng và kiểu dữ liệu của tham số | Số lượng và kiểu dữ liệu của tham số phải *giống nhau* |
| Kiểu trả về có thể *khác nhau*.                            | Kiểu trả về bắt buộc phải *giống nhau*.                |
| Xảy ra trong *cùng một class*                              | Xảy ra ở *2 class có quan hệ kế thừa*                  |

**Read more:**

https://codelearn.io/sharing/overiding-vs-overloading
https://viblo.asia/p/override-va-overload-WAyK8V4NlxX