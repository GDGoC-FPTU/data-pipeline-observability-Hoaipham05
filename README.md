[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574021&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** hoaihanh2501@gmail.com
**Name:** Phạm Thị Hoài
**Student ID:** 2A202600269

---

## Mo ta

Trong bai lab nay, minh xay dung mot ETL pipeline tu dong cho du lieu san pham.
Pipeline gom 4 buoc:

1. Extract du lieu JSON tu `raw_data.json`
2. Validate du lieu va loai bo record khong hop le (`price <= 0`, `category` rong)
3. Transform du lieu (chuan hoa `category`, tinh `discounted_price`, them `processed_at`)
4. Load ket qua ra `processed_data.csv`

Ngoai ra, minh thuc hien stress test bang `agent_simulation.py` tren clean data va garbage data de danh gia tac dong cua data quality den ket qua cua agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- So records extract: 5
- So records hop le sau validate: 3
- So records bi loai: 2
- File output tao thanh cong: `processed_data.csv`
- Test autograder: 9/9 passed

Ket qua stress test cho thay cung mot cau hoi nhung voi garbage data, agent co the dua ra ket qua vo ly do outlier va loi du lieu. Dieu nay khang dinh vai tro cua observability va data validation trong pipeline AI.
