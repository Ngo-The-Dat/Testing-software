**Faculty of Information Technology (FIT) – Ho Chi Minh City University of Science (HCMUS)**

**CS423 / CSC13003 – Software Testing (AI-augmented · 2026)**

**AI POLICY · TEMPLATES — 2026 v1.0**

# AI Use Disclosure Form

_Attach to assignments where AI was used in any permitted capacity._

_Adapted from Med Kharbach, PhD (2026) — AI Use Policy Templates for Higher Education. CC BY-NC-SA 4.0. This adaptation is prepared for FIT@HCMUS – CS423 / CSC15003 Software Testing course._

## 1\. Course & Student Info

| Field | Value |
| --- | --- |
| Course: | CS423 / CSC13003 – Software Testing |
| Assignment ID: | HW02 |
| Assignment Title: | Domain Testing |
| AI Use Category (1–5): | Category 2 |
| Date: | 27/06/2026 |
| Student name: | Ngô Thế Đạt |
| Student ID: | 23127340 |

## 2\. Disclosure Questions

### 1\. AI tool(s) used:

_List every AI tool used for this assignment (e.g., AI Tool (e.g., ChatGPT, Claude, Gemini), ChatGPT, GitHub Copilot, Cursor, Gemini)._

Claude, Gemini

### 2\. Stage(s) of the assignment where AI was used:

_Tick all that apply: \[x \] brainstorming \[x \] outlining \[ \] drafting \[ \] feedback \[ \] revision \[ \] coding \[ \] data analysis \[ \] visual design \[ \] other (specify)._

### 3\. Main prompts or tasks given to the AI:

_Paste the 2–3 most impactful prompts verbatim. For the full transcript, attach Appendix A (prompt\_log.md)._

**Prompt 1:**

Dựa vào @\[README.md\]. Viết cho tôi phần test design(Domain task áp dụng phương pháp Equivalance partitioning) của FR03 vào file @\[tests/test-design/EP-FR03.md\]. Format như sau:

1.  Xác định miền giá trị Input & Output Input: Bảng gồm 3 cột: Tên giá trị, số miền giá trị, miền hợp lệ, miền không hợp lệ(liệt kê các miền giá trị đó từng dòng 1) Output: Tương tự như input
2.  Test case 2.1. Test case cho miền hợp lệ Bảng chứa các test case hợp lệ trong đó phải có các cột sau: ID, Test objective, giá trị input và output.

2.2. Test case cho miền không hợp lệ Áp dụng tương tự 2.1

Lưu ý: Đây chỉ là test design, tuyệt đối không được test mà chỉ thiết kế test case thôi.

ID mẫu của test case hợp lệ là: FR03\_EP\_V01, FR03\_EP\_V02 ID mẫu của test case không hợp lệ là: FR03\_EP\_IV01, FR03\_EP\_IV02

Test objective thì đại loại là: Test giá trị a trong miền x hoặc test giá trị b trong miền y

**Prompt 2:**  
Dựa trên mô tả chức năng FR03 của @\[README.md\] và các input xác định được trong @\[tests/test-design/EP-FR03.md\] . Hãy viết cho tôi @\[tests/test-design/BVA-FR03.md\] áp dụng phương pháp boudary value analysis. Format như sau: Phương pháp: 3-Point Boundary Values (BVA) Yêu cầu tham chiếu: FR-03 (Quên mật khẩu & Đặt lại mật khẩu)

1.  Xác định input Trình bày bảng chứa các miền giá trị input hợp lệ
2.  Test case Trình bày bảng với các cột như sau:

*   ID: Với mẫu là FR03\_\[BoundaryType\]\_\[Sequence\] BoundaryType sẽ gồm có: MINM, MIN, MINP, MAXM,MAX,MAXP(M là minus(-1), P là Plus(+1))
*   Partition Tested
*   Các cột input
*   Expected Output

Expected output thì trình bày như bên@\[tests/test-design/EP-FR03.md\] (mục 3. Rút gọn TC)

**Prompt 3:**

Viết cho tôi template cho test-design của BVA và EP dựa trên @\[tests/test-design/BVA-FR03.md\] và @\[tests/test-design/EP-FR03.md\]. Đặt tên file là BVA\_template.md và EP\_template.md. BVA\_template sẽ, EP\_template là template khi design test case.

### 4\. Specific parts of the work AI contributed to:

_Be specific. Example: 'AI generated TC01–TC15 in Section 3.2; I rewrote TC04 and TC11; AI did NOT contribute to Sections 1, 2, 4, or the AI Critique.'_

### 5\. How I reviewed, revised, or verified the AI output:

_Describe your verification method (ran the test, checked the spec, asked the TA, looked up RFC, cross-checked with the ISTQB syllabus, etc.)._

I ran the test to check if the actual results were correct. I reviewed the material and checked if the test designs were correct as I had learned them. I check if the bugs actual exist by testing manually

### 6\. Citation (if required by course style guide):

_Software Testing uses the IEEE style. Example: Anthropic. (2026). AI Tool (e.g., ChatGPT, Claude, Gemini) \[Large language model\]. https://claude.ai_

\[1\] Google. (2026). Gemini (Version 3.5 Flash) \[Large language model\]. Available: [https://gemini.google.com](https://gemini.google.com)

\[2\] Anthropic. (2026). Claude (Version 4.6 Sonnet) \[Large language model\]. Available: [https://claude.ai](https://claude.ai)

## 3\. Statement of Honesty

_By signing below, I confirm that the disclosure above is accurate and complete. I understand that undisclosed or false disclosure of AI use is treated as academic misconduct and may result in a 0 grade for the assignment and disciplinary referral._

## Signature

| Student name (printed): | Ngô Thế Đạt |
| --- | --- |
| Student ID: | 23127340 |
| Class / Cohort: | 23KTPM3 |
| Course: | CS423 / CSC13003 – Software Testing |
| Instructor: | Hồ Tuấn Thanh |
| Date: | 27/06/2026 |
| Signature: |  |

## References

*   Kharbach, M. (2026). AI Use Policy Templates for Higher Education. CC BY-NC-SA 4.0.
*   ISTQB Foundation Level Syllabus (latest version).
*   Hardman, P. (2025). A Post-AI Learning Taxonomy.
*   Fuster Rabella, M. (2025). OECD Education Working Paper No. 338.
*   Perkins, M., Roe, J., & Furze, L. (2025). AI Assessment Scale.
*   Anthropic (2025). Building reliable AI test agents — engineering blog.
*   DeepEval & Promptfoo documentation — testing frameworks for LLM systems.