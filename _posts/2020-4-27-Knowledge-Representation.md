---
layout: post
categories: Artificial 
tittle: Knowledge Representation
--- 

# &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp; KNOWLEDGE REPRESENTATION
## &ensp;&ensp; Nhắc lại về mệnh đề logic

### Các khái niệm
* **Dạng chuẩn**: là kết xuất chuẩn của các giải thuật làm việc với phép toán mệnh đề
* **Tuyển cơ bản**: là thành phần cơ bản hay sự kết hợp của các thành phần cơ bản bằng phép tuyển (v)
* **Hội cơ bản**: tương tự nhưng bằng phép hội (^)
* **Dạng chuẩn hội-CNF**: là thành phần *tuyển* cơ bản hay các *tuyển* cơ bản kết hợp bới phép *hội*.(CNF: conjunctive normal form).

VD: (P₁ ∨...∨ Pₙ)₁ ∧ ... ∧ (Q₁ ∨...∨ Qₘ)ₚ, với n,m ≥ 1

* **Dạng chuẩn tuyển-DNF**: là thành phần *hội* cơ bản hay các *hội* cơ bản được kết hợp bới phép *tuyển*

### Nhắc lại về các phép toán với mệnh đề logic

1. **Phép phủ định**: phủ định của mệnh đề P là một mệnh đề, ký hiệu là ¬P.(**1 ngôi**)

Bảng chân trị:

| P    | ¬P    |
| -----|:-----:|
| 0    | 1     |
| 1    | 0     | 

2. **Phép hội**: của hai mệnh P, Q là 1 mệnh đề, kí hiệu là P∧Q (P và Q).(**2 ngôi**)

Bảng chân trị

| P    | Q     |&ensp; P ∧ Q |
| -----|:-----:|------:|
| 0    | 0     | 0     |
| 0    | 1     | 0     |
| 1    | 0     | 0     |
| 1    | 1     | 1     |

***Nhận xét***: P ∧ Q đúng khi và chỉ khi cả P và Q đồng thời đúng

3.**Phép tuyển**: của 2 mệnh đề P,Q là 1 mệnh đề, kí hiệu là P∨Q(P hay Q).(**2 ngôi**)

Bảng chân trị

| P    | Q     |&ensp; P ∨ Q |
| -----|:-----:|------:|
| 0    | 0     | 0     |
| 0    | 1     | 0     |
| 1    | 0     | 0     |
| 1    | 1     | 1     |

***Nhận xét***: P ∨ Q sai khi và chỉ khi cả P và Q đồng thời sai.

4. **Phép kéo theo**: Mệnh đề P kéo theo mệnh đề Q là 1 mệnh đề, kí hiệu P → Q(**2 ngôi**)

Bảng chân trị:

| P    | Q     |&ensp; P → Q |
| -----|:-----:|------:|
| 0    | 0     | 1     |
| 0    | 1     | 1     |
| 1    | 0     | 0     |
| 1    | 1     | 1     |

***Nhận xét***: P → Q sai khi và chỉ khi P đúng mà Q sai

5. **Phép kéo theo 2 chiều**: kí hiệu P ↔ Q.

Bảng chân trị:

| P    | Q     |&ensp; P ↔ Q |
| -----|:-----:|------:|
| 0    | 0     | 1     |
| 0    | 1     | 0     |
| 1    | 0     | 0     |
| 1    | 1     | 1     |

***Nhận xét***: P ↔ Q đúng khi và chỉ khi P và Q đều đúng hoặc đều sai (có cùng chân trị).

&ensp;&ensp;&ensp; **Ưu tiên của các toán tử logic**
* Ưu tiên mức 1: ()
* Ưu tiên mức 2: ¬
* Ưu tiên mức 3: ∨, ∧ 
* Ưu tiên mức 4: →, ↔

### Các luật LOGIC

1. Phủ định của phủ định: ¬¬P <=> P
2. Qui tắc De Morgan: 
    * ¬(P ∨ Q) <=> ¬P ∧ ¬Q
    * ¬(P ∧ Q) <=> ¬P ∨ ¬Q
3. Luật giao hoán: 
    * P ∨ Q <=> Q ∨ P
    * P ∧ Q <=> Q ∧ P
4. Luật kết hợp:
    * (P ∨ Q) ∨ R <=> P ∨ (Q ∨ R)
    * (P ∧ Q) ∧ R <=> P ∧ (Q ∧ R)
5. Luật phân phối:
    * P ∧ (Q ∨ R) <=> (P ∧ Q) ∨ (P ∧ R)
    * P ∨ (Q ∧ R) <=> (P ∨ Q) ∧ (P ∨ R)
6. Luật lũy đẳng:
    * P ∧ P <=> P
    * P ∨ P <=> P
7. Luật trung hòa:
    * P ∨ 0 <=> P
    * P ∧ 1 <=> P
8. Luật về phần tử bù:
    * P ∧ ¬P <=> 0
    * P ∨ ¬P <=> 1
9. Luật thống trị:
    * P ∧ 0 <=> 0
    * P ∨ 1 <=> 1
10. Luật hấp thu:
    * P ∨ (P ∧ Q) <=> P
    * P ∧ (P ∨ Q) <=> P
11. Luật về phép kéo theo: P → Q <=> ¬P ∨ Q <=> ¬Q → ¬P

### Các qui tắc suy diễn

## THUẬT TOÁN VƯƠNG HẠO

*Các bước thực hiện thuật toán VƯƠNG HẠO*

1. **B1:** Phát biểu lại giả thiết và kết luận của vấn đề theo dạng chuẩn sau:

GT₁, GT₂,..., GTₙ → KL₁,KL₂,...,KLₘ

2. **B2:** Chuyển vế các GTᵢ và KLᵢ có dạng phủ định

3. **B3:**
    * Nếu ở GTᵢ có phép ∧ thì thay phép ∧ bằng dấu **,**
    * Nếu ở KLᵢ có phép ∨ thì thay phép ∨ bằng dấu **,**
    
***Lưu ý***:

Không áp dụng với những trường hợp như sau:

**R ∨ (P ∧ Q) → P**

4. **B4:**
    * Nếu ở GTᵢ có phép ∨ thì tách thành 2 dòng con
    * Nếu ở KLᵢ có phép ∧ thì tách thành 2 dòng con
    
5. **B5:** Một mệnh đề được chứng minh nếu tồn tại chung 1 mệnh đề ở 2 phía.

6. **B6:**
    * Nếu 1 dòng không còn phép nối hoặc ở cả 2 vế và ở 2 vế không có chung 1 biến mệnh đề thì dòng đó không đc c/m
    * Một vấn đề được chứng minh nếu tất cả dòng dẫn xuất từ dạng chuẩn ban đầu đều được c/m.
    
## THUẬT TOÁN ROBINSON

* **Ý tưởng**: dựa trên phương pháp chứng minh phản chứng.

* **Các bước thực hiện**:
    * *B1:* 
        *   Phát biểu lại giả thiết dưới dạng chuẩn sau:
    
        GT₁, GT₂,..., GTₙ → KL₁,KL₂,...,KLₘ

        *   Trong đó: GTᵢ và KLᵢ được xây dựng từ các biến mệnh đề và các phép toán: ∨, ∧, ¬.

    * *B2:* 
        * Nếu ở GTᵢ có phép ∧ thì thay phép ∧ bằng dấu **,**
        * Nếu ở KLᵢ có phép ∨ thì thay phép ∨ bằng dấu **,**
    * *B3*: 
        *   Biến đổi dòng chuẩn ở B1 về thành danh sách mệnh đề như sau:

        [GT₁, GT₂,..., GTₙ,¬KL₁,¬KL₂,...,¬KLₘ]
    * *B4*:
    &ensp;Nếu trong danh sách mệnh đề tạo được ở b3, có **2 mệnh đề đối ngãu nhau** thì bài toán được chứng minh. Ngược lại chuyển sang b5. (a và ¬a được gọi là 2 mệnh đề đối ngẫu).
    * *B5*:
    &ensp;Xây dựng một mệnh đề mới bằng cách tuyển một cặp mệnh đề trong danh sách mệnh đề ở B3. Nếu mệnh đề mới có các biến mệnh đề đối ngãu nhau thì các biến đó được loại bỏ.
    
    &ensp;VD:

    p ∨ ¬q ∨ ¬r ∨ s ∨ q

    Do 2 mệnh đề q và ¬q đối ngẫu nên được loại bỏ.

    => p ∨ ¬r ∨ s
    
    * *B6*:

    &ensp;Thay thế 2 mệnh đề vừa tuyển trong danh sách thành mệnh đề đã được xử lý.

    * *B7*: Nếu không xây dựng được thêm 1 mệnh đề mới nào và trong danh sách mệnh đề không có 2 * mệnh đề đối ngẫu* thì vấn đề không được chứng minh.



