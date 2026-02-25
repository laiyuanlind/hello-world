# Python 新人标准仓库模板清单

> 目标：帮助新人从 0 到 1 搭建一个「可运行、可测试、可协作」的 Python 项目仓库。

## 1. 推荐目录结构（最小可用）

```text
your-project/
├─ src/
│  └─ your_package/
│     ├─ __init__.py
│     └─ main.py
├─ tests/
│  ├─ __init__.py
│  └─ test_main.py
├─ .github/
│  └─ workflows/
│     └─ ci.yml
├─ .gitignore
├─ README.md
├─ LICENSE
├─ pyproject.toml
├─ requirements.txt
├─ requirements-dev.txt
└─ Makefile
```

## 2. 必备文件清单（新人优先级）

### A. 基础说明
- [ ] `README.md`
  - [ ] 项目简介（做什么）
  - [ ] 快速开始（安装 + 运行）
  - [ ] 测试命令
  - [ ] 常见问题（FAQ）
- [ ] `LICENSE`（个人学习可先 MIT）
- [ ] `.gitignore`（Python 缓存、虚拟环境、IDE 文件）

### B. 依赖与打包
- [ ] `pyproject.toml`
  - [ ] 项目元信息（name/version/description）
  - [ ] 代码风格工具配置（如 ruff/black）
  - [ ] 测试配置（pytest）
- [ ] `requirements.txt`（生产依赖）
- [ ] `requirements-dev.txt`（开发依赖：pytest、ruff、black 等）

### C. 代码与测试
- [ ] `src/your_package/`（使用 `src` 布局）
- [ ] `tests/`（至少覆盖核心函数）
- [ ] 至少 1 个可运行入口（如 `python -m your_package.main`）

### D. 工程化与协作
- [ ] `.github/workflows/ci.yml`
  - [ ] 安装依赖
  - [ ] 运行格式检查
  - [ ] 运行测试
- [ ] `Makefile`
  - [ ] `make setup`（安装依赖）
  - [ ] `make lint`（代码检查）
  - [ ] `make test`（运行测试）

---

## 3. 推荐工具（新人友好）

- 测试：`pytest`
- Lint：`ruff`
- 格式化：`black`
- 覆盖率：`pytest-cov`
- 类型检查（可选）：`mypy`

> 新手建议：先把 `pytest + ruff + black` 跑通，再加 `mypy`。

---

## 4. 初始化步骤（可直接照做）

1. 创建虚拟环境并激活：
   - `python -m venv .venv`
   - `source .venv/bin/activate`（Windows 用 `.venv\\Scripts\\activate`）
2. 安装开发依赖：
   - `pip install -r requirements-dev.txt`
3. 首次检查：
   - `ruff check .`
   - `black --check .`
   - `pytest -q`
4. 提交前检查：
   - `make lint && make test`

---

## 5. 新人常见坑位提醒

- [ ] 不要把 `.venv/` 提交到仓库（靠 `.gitignore`）
- [ ] 不要直接在 `main` 分支开发，使用功能分支
- [ ] 每次提交只做一件事（小步提交）
- [ ] 每个新功能至少补 1 个测试
- [ ] README 要保证别人能复制命令后跑起来

---

## 6. 一份最小 `.gitignore`（Python）

```gitignore
__pycache__/
*.py[cod]
*.egg-info/
.venv/
.pytest_cache/
.mypy_cache/
.ruff_cache/
.coverage
htmlcov/
.vscode/
.idea/
```

---

## 7. 一份最小 `Makefile`（示例）

```make
setup:
	pip install -r requirements-dev.txt

lint:
	ruff check .
	black --check .

test:
	pytest -q
```

---

## 8. 建议学习路径（2 周）

### 第 1 周：把工程跑通
- Day 1-2：搭目录 + 依赖管理 + 可运行入口
- Day 3-4：写 3~5 个 pytest 用例
- Day 5：接入 ruff/black + 修复所有问题

### 第 2 周：提升可维护性
- Day 6-7：接入 GitHub Actions CI
- Day 8-9：补充 README 与 FAQ
- Day 10-12：学习分支与 PR 规范
- Day 13-14：给项目加一个小功能并完整走一遍提交流程

---

## 9. 你可以马上执行的 TODO

- [ ] 新建以上目录结构
- [ ] 填写 `pyproject.toml` / `requirements-dev.txt`
- [ ] 写一个 `hello` 功能 + 一个测试
- [ ] 配置 CI 并让它通过
