# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **static content repository** for ViralMaker (바이럴메이커), a Korean experience/review campaign service. It serves static assets to the mobile application.

## Repository Structure

```
viralmaker-static/
├── app/              # App icons and splash images (webp, png)
├── static/notice/    # Korean markdown notices with accompanying images
├── docs/             # Workflow documentation
└── xnotes/           # Project templates and notes
```

## Content Types

- **Notice files** (`static/notice/*.md`): Korean-language notices displayed in the app (launch announcements, purchase guides, error notices, payout info)
- **Notice images** (`static/notice/*.webp`): Accompanying images for notices
- **App assets** (`app/`): App icons and promotional images

## Development Notes

- **No build system**: This is a pure static content repository with no compilation or bundling
- **No package.json**: No Node.js dependencies or scripts
- **Git-based deployment**: Content changes are deployed via git commits

## Content Guidelines

When editing Korean markdown notices in `static/notice/`:

### Document Structure

1. **Opening**: Start with greeting `안녕하세요, **바이럴메이커**입니다.` (bold brand name for regular notices, plain for error notices)
2. **Introduction**: Brief paragraph explaining the notice topic
3. **Body**: Organized sections with `---` horizontal rule separators
4. **Closing**: End with `감사합니다.` followed by `**바이럴메이커 드림**` signature

### Heading Hierarchy

- **Main sections**: Use `## ` with emoji prefix (e.g., `## 🤔 바이럴메이커를 만든 이유`)
- **Subsections**: Use `#### ` with emoji or numbered prefix (e.g., `#### 1. 📅 체험단 일정 관리`)
- **Never use** `#`, `###`, or `#####` for content headings

### Common Section Emoji Patterns

| Section Type | Emoji | Example |
|--------------|-------|---------|
| Explanation/Question | 🤔 | `## 🤔 구매형 체험단이란?` |
| Confirmation/Checklist | ✅ | `## ✅ 신청 전 필수 확인 사항` |
| Warning/Caution | ⚠️ | `## ⚠️ 주의사항` |
| Process/Procedure | 🚀 | `## 🚀 진행 절차` |
| Summary | 💬 or 📌 | `## 💬 3줄 요약` |
| Contact Info | 📞 | `## 📞 문의 안내` |
| Money/Payment | 💰 | `## 💰 바이럴 포인트 출금 안내` |
| FAQ | ❓ | `## ❓ 씨앗 등급이란?` |
| Review/Writing | ✍ | `## ✍ 방문 후 리뷰 작성` |
| Search/Verification | 🔎 | `## 🔎 리뷰 검수` |

### Formatting Conventions

- **Bold emphasis**: Key terms and brand name `**바이럴메이커**`, `**바로 선정 체험단**`
- **UI elements**: Use brackets `[미션 완료]`, `[문의하기]`, `[방문 확인]`
- **Bullet lists**: Use `-` for unordered lists
- **Numbered subsections**: Use `#### 1.`, `#### 2.` format (with optional emoji)
- **Vertical spacing**: Use empty `###` lines between major sections
- **Section separators**: Use `---` between major content blocks

### Error Notice Format

Error notices (`*_error.md`) follow a simpler format:
1. Plain greeting: `안녕하세요, 바이럴메이커입니다.`
2. Problem description paragraph
3. `✅ 임시 해결 방법` section
4. `✅ 패치 및 추가 안내` section
5. `✅ 마감 기한 연장 안내` section
6. Apology: `서비스 이용에 불편을 드려 죄송합니다...`
7. `감사합니다.` closing (no signature block)

### Standard Closing Block

```markdown
---

## 📞 문의 안내
기타 궁금한 사항이 있으시면 **앱 내 [문의하기] 기능**을 통해 문의해 주세요.
바이럴메이커는 메이커님들의 원활한 체험단 활동을 위해 항상 최선을 다하겠습니다.

감사합니다.
**바이럴메이커 드림**
```

---

## Notice Image Guidelines

All notice images in `static/notice/` follow consistent design specifications.

### Image Specifications

| Property | Value |
|----------|-------|
| **Dimensions** | 1600 × 900 pixels |
| **Aspect Ratio** | 16:9 |
| **Format** | WebP (preferred), PNG (fallback) |
| **File Size** | 17-70 KB (WebP), ~435 KB (PNG) |
| **Naming** | Match markdown filename (e.g., `purchase.md` → `purchase.webp`) |

### Image Types by Category

#### 1. Guide Images (가이드)
- **Background**: Light lavender/blue-gray (`#E8EAF0` or similar)
- **Badge**: Rounded rectangle, top-left corner
  - Green badge for general guides: `가이드` (white text, green `#7CB342` background)
  - Blue badge for specific features: `가이드` (white text, blue `#42A5F5` background)
- **Illustration**: 3D cartoon/clay-style object on right side
- **Text**: Bold Korean title on left side, black or dark text
- **Examples**: `payout.webp`, `purchase.webp`

#### 2. Error/Urgent Images (긴급)
- **Background**: Dark charcoal/black (`#2D2D2D` or `#1A1A1A`)
- **Badge**: Red rounded rectangle, top-left: `긴급` (white text, red `#E53935` background)
- **Illustration**: 3D construction barrier (orange/white stripes), centered bottom
- **Text**: White text with black stroke, centered, large bold Korean
- **Examples**: `purchase_error.webp`, `smartstore_error.webp`

#### 3. Announcement Images (안내)
- **Background**: Thematic solid color (e.g., dark green `#2E5339` for seed)
- **Badge**: Green rounded rectangle, top-left: `안내` (white text, green background)
- **Illustration**: Multiple 3D objects related to theme, scattered layout
- **Text**: Cream/light colored Korean text on left side
- **Brand Logo**: VM logo integrated into illustration
- **Examples**: `seed.webp`

#### 4. Launch/Special Images
- **Background**: Dark navy space gradient with subtle glow
- **Illustration**: 3D rocket with VM brand logo, launching with smoke clouds
- **Text**: "VIRAL MAKER" in English + Korean subtitle (e.g., `출시`)
- **Decorative**: Golden 4-point stars scattered
- **No badge**: Special announcements don't use category badges
- **Examples**: `launch.webp`

#### 5. Photo-Based Images
- **Background**: AI-generated realistic photo (restaurant, store scene)
- **Text**: White bold Korean text with black stroke/outline, centered
- **Style**: Text overlay on photo, high contrast for readability
- **Examples**: `visit.webp`

### Design Elements

#### Badge Specifications
```
Position: Top-left corner (approx. 50px from edges)
Shape: Rounded rectangle (border-radius ~12px)
Size: ~140×60 pixels
Font: Bold, white Korean text
```

| Badge Type | Korean Text | Background Color |
|------------|-------------|------------------|
| Guide | 가이드 | Green `#7CB342` or Blue `#42A5F5` |
| Urgent | 긴급 | Red `#E53935` |
| Announcement | 안내 | Green `#7CB342` |

#### 3D Illustration Style
- **Aesthetic**: Soft, rounded, clay/cartoon style (similar to Blush/3D Icons)
- **Lighting**: Soft shadows, subtle gradients
- **Colors**: Vibrant but not oversaturated
- **Brand Integration**: Include VM/VAI logo on relevant objects (rocket, pot, etc.)

#### Typography
- **Korean Title Font**: Bold sans-serif (similar to Pretendard, Spoqa Han Sans)
- **English Brand**: "VIRAL MAKER" in custom brand font
- **Text Effects**:
  - Light backgrounds: Plain dark text
  - Dark backgrounds: White text with subtle black stroke for contrast

### AI Image Generation Prompts

When generating new notice images, use these prompt templates:

#### For Guide Images:
```
Create a 16:9 promotional banner with light lavender background (#E8EAF0).
Place a 3D cartoon-style [OBJECT] illustration on the right side.
Leave space on the left for Korean text overlay.
Style: soft clay/3D render, rounded edges, soft shadows.
```

#### For Error Images:
```
Create a 16:9 notice banner with dark charcoal background (#2D2D2D).
Place a 3D cartoon construction barrier (orange and white stripes) in the center-bottom.
Style: soft 3D render, matte finish.
Leave space for white text overlay with black stroke in the upper portion.
```

#### For Announcement Images:
```
Create a 16:9 banner with solid [COLOR] background.
Include multiple 3D cartoon-style objects related to [THEME], scattered across the right side.
Style: soft clay/3D render, playful arrangement.
Leave space on the left for light-colored text.
```

### File Naming Convention

| Notice Type | Markdown | Image |
|-------------|----------|-------|
| Standard guide | `{feature}.md` | `{feature}.webp` |
| Error notice | `{feature}_error.md` | `{feature}_error.webp` |

### Quality Checklist

Before adding a new notice image:
- [ ] Dimensions: 1600×900 pixels
- [ ] Format: WebP preferred (PNG acceptable)
- [ ] File size: Under 100KB for WebP
- [ ] Matches markdown filename
- [ ] Badge type matches content category
- [ ] Text is readable (sufficient contrast)
- [ ] Brand consistency (VM logo if applicable)
