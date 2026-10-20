# Data Visualization: Group Homework 4

My group keeps its work for Group Homework 4 of the Data Visualization course in this repository. In this homework, my group looks for hidden groups among the 140 pickup stores of GoMart. We standardize the nine numbers of each store, reduce them with PCA, cluster them with k-means, name the groups from their behaviour, and test whether the groups are real. GoMart is a made-up online grocery service, and all of its data is simulated.

Team name: Team 10, after the team number on the LMS list. The notebook for the hand-in is `GH4_Team10.ipynb`.

## Members and branches

Each member works on their own branch.

| Member | Branch |
|---|---|
| Nguyễn Hoàng Minh (leader) | `hwinh` |
| Phạm Quang Minh | `quang-minh` |
| Phạm Tuấn Anh | `tuan-anh` |
| Trần Nhã Đoan | `nha-doan` |
| Nguyễn Minh Nguyệt | `minh-nguyet` |
| Trần Nguyễn Thanh Thảo | `thao` |

## How my group works together

A member never pushes to `dev` or `main` directly. A member pushes to their own branch and then opens a pull request into `dev`. The leader reads the pull request and merges it. When my group is ready to hand in the work, the leader opens a pull request from `dev` into `main`.

GitHub enforces these rules for us:

- The `main` branch accepts pull requests only from `dev`, and only the repository owner can merge them. Nobody can push to `main` directly, and the owner cannot either.
- The `dev` branch accepts changes only through pull requests. Every member can open one, and only the repository owner can merge it.
- A pull request into `main` from any other branch fails the check named `chi-nhan-tu-dev`. A pull request into `main` that a member opens is also closed automatically.
- Nobody can delete a member branch.

### Steps for a member

First, download the repository and switch to your own branch. The example below uses the branch `thao`.

```bash
git clone https://github.com/hwinhwork-dot/DataViz_Day04_Group.git
cd DataViz_Day04_Group
git checkout thao
```

Before you start working, pull the newest work from `dev`.

```bash
git pull origin dev
```

When you finish a piece of work, save it and push it to your own branch.

```bash
git add .
git commit -m "Short description of the change"
git push origin thao
```

Last, open GitHub, go to Pull requests, and choose New pull request. Set the base branch to `dev` and the compare branch to your own branch.

Two members should not edit `GH4_Team10.ipynb` at the same time, because a notebook is hard to merge. Each member works in a draft notebook of their own, and the leader copies the finished part into the main notebook.

## What my group hands in

| File | Task |
|---|---|
| `homework/gh4_gomart_stores/GH4_Team10.ipynb` | Tasks 0 to 7, with the memo at the top. It starts from `homework04_starter.ipynb`. |

The notebook is the only file of the hand-in. It has to run from top to bottom after Restart and run all. We do not hand in the data file, because the lecturer has it.

## The data

`data/raw/gomart_stores_2025.csv` has one row per store and 140 stores in total. We never edit this file.

| Column | Role |
|---|---|
| `store_id` | The label of the store, for example `S001`. It is not a feature. |
| `orders_per_day`, `avg_basket_k`, `median_delivery_min`, `ontime_share`, `ewallet_share`, `promo_order_share`, `evening_share`, `repeat_customer_share`, `items_per_order` | The nine features that go into PCA and k-means, after standardizing. |
| `zone` | Central, Inner or Outer. It is context: we use it to describe the groups afterwards and never to compute distances. |

We keep the file in the repository so that every member works with the same numbers. It is not part of the hand-in, so we do not upload it to the LMS.

## Folders

```
.
├── homework/
│   └── gh4_gomart_stores/   the hand-in set: the notebook GH4_Team10.ipynb
├── data/
│   └── raw/                 gomart_stores_2025.csv from the LMS, which we never edit
└── requirements.txt         The Python packages that we use
```

## Setup

The commands below create a virtual environment and install the packages. `scikit-learn` and `scipy` are the packages for PCA, k-means and Ward clustering.

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```
