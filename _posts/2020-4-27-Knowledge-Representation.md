---
layout: Artificial Intelligence
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

1. **Phép phủ định**: phủ định của mệnh đề P là một mệnh đề, ký hiệu là ¬P.

Bảng chân trị:
| P    | ¬P    |
| -----|:-----:|
| 0    | 1     |
| 1    | 0     | 

