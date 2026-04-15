# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600269
**Name:** Phạm Thị Hoài
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Tra loi hop ly, gia cao nhat trong category electronics sau khi du lieu da duoc lam sach. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Bi outlier chi phoi ket qua, Agent chon san pham vo ly vi khong co buoc kiem soat chat luong du lieu. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung garbage data, Agent tra loi sai vi logic truy van phu thuoc truc tiep vao du lieu dau vao ma khong co lop bao ve chat luong. Ban ghi outlier "Nuclear Reactor" co gia 999999 lam sai lech tieu chi chon "best" theo gia cao nhat. Ngoai ra, tap du lieu ban co duplicate ID, kieu du lieu gia khong dong nhat (chuoi "ten dollars"), va gia tri null. Cac loi nay khien he thong de bi nham lan, tao ket qua khong con phan anh ngu canh mua sam thong thuong. Neu pipeline bo sung validation, type checking, outlier detection va schema constraints truoc khi nap du lieu vao Agent, do tin cay cau tra loi se tang ro ret.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Dong y. Prompt tot chi co tac dung khi du lieu nen dung va du tin cay. Neu du lieu bi nhiem loi, Agent van co the suy luan sai du prompt rat ro rang. Trong bai nay, cung mot truy van nhung ket qua chenh lech lon giua clean va garbage data cho thay chat luong du lieu la dieu kien tien quyet de AI hoat dong on dinh.
