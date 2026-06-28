# 生图提示词模板

这是 layer 0 通用模板。每张图单独生成。根据内容与上层场景替换变量，不要把多张图拼在一起。

```text
Design one standalone Xiaodai illustration for the scene decision below.

Scene mode:
{scene_mode}

Format goal:
{format_goal}

Canvas ratio:
{canvas_ratio}

Subject density:
{subject_density}

Visual DNA:
Pure white background. Minimalist black hand-drawn line art. Slightly wobbly pen lines. Lots of empty white space. Sparse red/orange/blue handwritten Chinese annotations. Clean absurd product-sketch feeling. No gradients, no shadows, no paper texture, no complex background, no commercial vector style, no PPT infographic look, no cute mascot poster, no children's illustration, no realistic UI.

Recurring IP character (小呆) — from reference image:
小呆, a little flame person (小火人), which is a small solid red flame-shaped silhouette character with two small white-dot eyes and thin black stick-figure limbs (arms and legs). No hair, no clothing details, no glasses, no shoes. Serious but doing something absurd, participating as the core operator in the conceptual action. Keep the character serene, focused, and slightly bizarre.

Theme:
{配图主题}

Structure type:
{结构类型：Workflow / 系统局部 / 前后对比 / 角色状态 / 概念隐喻 / 方法分层 / 地图路线 / 小漫画分镜}

Core idea:
{这张图要表达的核心意思}

Core metaphor:
{这次选用的物理隐喻}

Composition:
{具体画面：小呆在哪里、正在做什么、主要物件是什么、信息如何流动}

Suggested elements:
{元素1} / {元素2} / {元素3} / {元素4}

Chinese handwritten labels:
{标注词1} / {标注词2} / {标注词3} / {标注词4} / {可选标注词5}

Color use:
Black for main line art. Solid bright red for the character 小呆. Orange for main flow/path/arrows. Red only for key warnings/problems/results. Blue only for secondary notes or feedback/system state.

Constraints:
One image explains only one core structure. Keep the main subject around 40%-60% of the canvas. Preserve at least 35% blank white space. Use at most 5-8 short handwritten Chinese labels. Do not write a title in the top-left corner. Do not write the structure type on the image. Do not make it a formal diagram, course slide, or dense explainer. Do not copy prior examples or reuse known case compositions unless explicitly requested; invent a fresh visual metaphor for this specific article. It should be clear but not instructional, interesting but not childish, strange but clean.
```

## 使用顺序

如果用户没有给完整的场景规格，先输出一段简短的 scene decision，再填这个模板。

推荐最小 decision 字段：

- `scene_mode`
- `format_goal`
- `canvas_ratio`
- `subject_density`
- `structure_type`
- `core_metaphor`

不要把 `Canvas ratio: 16:9 horizontal` 这种字段写成系统默认值；它应该是当前任务的判断结果。

字段边界：

- `scene_mode` = 使用场景
- `structure_type` = 表达结构

`scene_mode` 不要写成 `conceptual_metaphor`、`workflow`、`before_after` 这类结构词。

例如：

- `scene_mode: article_inline`
- `scene_mode: social_single`
- `scene_mode: feed_cover`
- `scene_mode: vertical_cover`
- `structure_type: conceptual_metaphor`

## 图像编辑提示

增强存在感：

```text
Regenerate this illustration with the same core meaning and simple layout, but make the red flame character 小呆 more central to the conceptual action. 小呆 should be doing the strange work that explains the idea, not standing beside the diagram. Keep it clean, sparse, hand-drawn, and not cute.
```
