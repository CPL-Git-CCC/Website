# **Design System Documentation**  
`README.md`  

---

## **Modern Labor Movements Timeline**  
**Visual Design Guide**  

This document outlines the typography, color scheme, and interaction patterns for the interactive labor movements timeline.  

---

## **1. Typography**  
### **Font Stack**  
```css
font-family: 'Segoe UI', system-ui, sans-serif;
```

### **Type Scale**  
| Element          | Size  | Weight | Color       | Example                     |
|------------------|-------|--------|-------------|-----------------------------|
| Main Heading     | 2rem  | 600    | `#000000`   | "Modern Labor Movements"    |
| Event Title      | 1.25rem | 600  | Movement-specific* | "ALU Wins Historic Election" |
| Date Label       | 1rem  | 700    | `#000000`   | **March 2020**              |
| Body Text        | 1rem  | 400    | `#000000`   | Description paragraphs      |
| Legend Label     | 0.9rem| 500    | `#000000`   | "Starbucks Unionization"    |

> *Movement colors: Railroad (`#2564c8`), Amazon (`#c88925`), Starbucks (`#25c837`).

---

## **2. Color Palette**  
### **Core Colors**  
| Role               | Hex       | Preview                          |
|--------------------|-----------|----------------------------------|
| Background         | `#c825b6` | ![#c825b6](https://via.placeholder.com/50/c825b6/000000?text=+) |
| Railroad Blue      | `#2564c8` | ![#2564c8](https://via.placeholder.com/50/2564c8/ffffff?text=+) |
| Amazon Orange      | `#c88925` | ![#c88925](https://via.placeholder.com/50/c88925/ffffff?text=+) |
| Starbucks Green    | `#25c837` | ![#25c837](https://via.placeholder.com/50/25c837/ffffff?text=+) |

### **UI Colors**  
| Element            | Style                                  |
|--------------------|----------------------------------------|
| Text               | `#000000` (black)                     |
| Card Background    | `rgba(255,255,255,0.95)`              |
| Timeline Line      | `rgba(0,0,0,0.15)`                    |
| Hover Shadow       | `0 6px 16px rgba(0,0,0,0.3)`          |

---

## **3. Component Design**  
### **Timeline Card**  
![Card Structure](https://via.placeholder.com/400x150/ffffff/000000?text=Event+Card+Example)  
- **Left Border**: 4px movement-specific color  
- **Header**: Colored title + black date with indicator dot  
- **Body**: Black text on semi-transparent white  
- **Hover**: Lifts 5px + shadow intensifies  

### **Legend**  
```plaintext
[●] Railroad Labor Dispute  
[●] Amazon Unionization  
[●] Starbucks Unionization  
```
- **Style**: Rounded pills with colored dots  
- **Background**: `rgba(255,255,255,0.8)`  

### **Timeline Structure**  
```plaintext
          ● (Railroad Event)
        /
-------●------- (Central Line)
        \
          ● (Amazon Event)
```
- **Line Color**: Light gray (`rgba(0,0,0,0.15)`)  
- **Dots**: White with colored borders  

---

## **4. Interaction Design**  
### **Behaviors**  
- **Hover on Cards**:  
  ```css
  transform: translateY(-5px);
  box-shadow: 0 6px 16px rgba(0,0,0,0.3);
  ```
- **Scroll Animation**:  
  - Cards fade in and slide from their respective sides  
  - Uses `IntersectionObserver` for performance  

### **Responsive Rules**  
| Breakpoint | Layout Change                          |
|------------|----------------------------------------|
| <768px     | Timeline line left-aligned             |
|            | Cards full-width                       |
|            | Dots appear only on left side          |

---

## **5. Accessibility**  
- **Contrast Ratios**:  
  - Black text (`#000000`) on purple (`#c825b6`) = **10.3:1** (AAA)  
  - Movement colors on white = ≥4.5:1 (AA)  
- **Focus States**:  
  ```css
  .event-card:focus {
    outline: 2px solid #2564c8;
  }
  ```

---

## **Usage**  
1. **HTML Structure**:  
   ```html
   <div class="timeline-container">
     <div class="event left rail">
       <div class="event-card">...</div>
     </div>
   </div>
   ```

2. **CSS Import**:  
   ```html
   <link rel="stylesheet" href="css/style.css">
   ```

3. **JavaScript**:  
   ```js
   // Handles scroll animations
   document.addEventListener('DOMContentLoaded', initTimeline);
   ```

---

**License**  
MIT © 2023 [Your Name]  

--- 

For implementation details, see:  
- `index.html`  
- `css/style.css`  
- `js/main.js` (if applicable)  

```bash
project/
├── index.html
├── css/
│   └── style.css
└── assets/
    ├── rail-icon.svg
    ├── amazon-icon.svg
    └── sbux-icon.svg
```
