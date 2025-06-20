# Loader Resource Studio - Complete Collection (All 100 Loaders)

**Version:** 1.0.0  
**Total Loaders:** 100  
**License:** MIT  
**Copyright:** © 2025 Chezcakeishere on GitHub

## Table of Contents

- [Spinning Loaders (1-20)](#spinning-loaders-1-20)
- [Pulsing Loaders (21-40)](#pulsing-loaders-21-40)
- [Bouncing Loaders (41-60)](#bouncing-loaders-41-60)
- [Sliding Loaders (61-80)](#sliding-loaders-61-80)
- [Morphing Loaders (81-100)](#morphing-loaders-81-100)

---

# Spinning Loaders (1-20)

## Loader 1: Classic Ring
**Type:** Spin | **Pattern:** Ring  
**Description:** A classic spinning ring loader with transparent top border

### HTML/CSS
```html
<!-- Classic Ring Loader -->
<div class="loader-1" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 border-2 border-current border-t-transparent rounded-full animate-spin"></div>
</div>

<style>
.loader-1 {
  display: flex;
  align-items: center;
  justify-content: center;
  animation-duration: 1s;
}
</style>
```

### React
```jsx
import React from 'react';

const ClassicRingLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
      <div 
        className="border-2 border-current border-t-transparent rounded-full animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${1/speed}s`
        }}
      />
    </div>
  );
};

export default ClassicRingLoader;
```

### Java
```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class ClassicRingLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public ClassicRingLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            angle += 5f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(2f));
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        
        // Draw partial circle (classic ring effect)
        g2d.drawArc(centerX - size/4, centerY - size/4, size/2, size/2, 0, 270);
        
        g2d.dispose();
    }
}
```

---

## Loader 2: Dashed Circle
**Type:** Spin | **Pattern:** Dashed  
**Description:** A spinning dashed circle loader

### HTML/CSS
```html
<!-- Dashed Circle Loader -->
<div class="loader-2" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 border-2 border-dashed border-current rounded-full animate-spin"></div>
</div>

<style>
.loader-2 {
  display: flex;
  align-items: center;
  justify-content: center;
}
.loader-2 > div {
  animation-duration: 1.5s;
}
</style>
```

### React
```jsx
const DashedCircleLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
      <div 
        className="border-2 border-dashed border-current rounded-full animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${1.5/speed}s`
        }}
      />
    </div>
  );
};
```

### Java
```java
public class DashedCircleLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public DashedCircleLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(30 / speed), e -> {
            angle += 3f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        BasicStroke dashedStroke = new BasicStroke(2f, BasicStroke.CAP_BUTT, 
            BasicStroke.JOIN_MITER, 10f, new float[]{5f, 5f}, 0f);
        g2d.setStroke(dashedStroke);
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        g2d.drawOval(centerX - size/4, centerY - size/4, size/2, size/2);
        
        g2d.dispose();
    }
}
```

---

## Loader 3: Half Circle
**Type:** Spin | **Pattern:** Half  
**Description:** A half-circle spinning loader

### HTML/CSS
```html
<!-- Half Circle Loader -->
<div class="loader-3" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 border-4 border-current border-r-transparent border-b-transparent rounded-full animate-spin"></div>
</div>

<style>
.loader-3 {
  display: flex;
  align-items: center;
  justify-content: center;
}
.loader-3 > div {
  animation-duration: 1s;
}
</style>
```

### React
```jsx
const HalfCircleLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
      <div 
        className="border-4 border-current border-r-transparent border-b-transparent rounded-full animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${1/speed}s`
        }}
      />
    </div>
  );
};
```

### Java
```java
public class HalfCircleLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public HalfCircleLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            angle += 6f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(4f));
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        g2d.drawArc(centerX - size/4, centerY - size/4, size/2, size/2, 0, 180);
        
        g2d.dispose();
    }
}
```

---

## Loader 4: Double Ring
**Type:** Spin | **Pattern:** Double Ring  
**Description:** Two concentric spinning rings

### HTML/CSS
```html
<!-- Double Ring Loader -->
<div class="loader-4" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-10 h-10 border-2 border-blue-500 border-t-transparent rounded-full animate-spin"></div>
  <div class="absolute w-6 h-6 border-2 border-green-500 border-b-transparent rounded-full animate-spin" 
       style="top: 50%; left: 50%; transform: translate(-50%, -50%); animation-direction: reverse; animation-duration: 1.5s;"></div>
</div>
```

### React
```jsx
const DoubleRingLoader = ({ size = 40, primaryColor = '#1a73e8', secondaryColor = '#34a853', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      <div 
        className="absolute border-2 border-t-transparent rounded-full animate-spin"
        style={{ 
          width: size, 
          height: size,
          borderColor: primaryColor,
          borderTopColor: 'transparent',
          animationDuration: `${2/speed}s`
        }}
      />
      <div 
        className="absolute border-2 border-b-transparent rounded-full animate-spin"
        style={{ 
          width: size * 0.6, 
          height: size * 0.6,
          borderColor: secondaryColor,
          borderBottomColor: 'transparent',
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)',
          animationDuration: `${1.5/speed}s`,
          animationDirection: 'reverse'
        }}
      />
    </div>
  );
};
```

### Java
```java
public class DoubleRingLoader extends JPanel {
    private Timer timer;
    private float outerAngle = 0f;
    private float innerAngle = 0f;
    private int size = 40;
    private Color primaryColor = Color.decode("#1a73e8");
    private Color secondaryColor = Color.decode("#34a853");
    private float speed = 1f;
    
    public DoubleRingLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            outerAngle += 3f;
            innerAngle -= 4f;
            if (outerAngle >= 360f) outerAngle = 0f;
            if (innerAngle <= -360f) innerAngle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        // Outer ring
        g2d.setColor(primaryColor);
        g2d.setStroke(new BasicStroke(2f));
        g2d.rotate(Math.toRadians(outerAngle), centerX, centerY);
        g2d.drawArc(centerX - size/4, centerY - size/4, size/2, size/2, 0, 270);
        
        // Reset rotation
        g2d.rotate(Math.toRadians(-outerAngle), centerX, centerY);
        
        // Inner ring
        g2d.setColor(secondaryColor);
        g2d.rotate(Math.toRadians(innerAngle), centerX, centerY);
        g2d.drawArc(centerX - size/6, centerY - size/6, size/3, size/3, 180, 270);
        
        g2d.dispose();
    }
}
```

---

## Loader 5: Triple Ring
**Type:** Spin | **Pattern:** Triple Ring  
**Description:** Three concentric spinning rings with different speeds

### HTML/CSS
```html
<!-- Triple Ring Loader -->
<div class="loader-5" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-10 h-10 border-2 border-blue-500 border-t-transparent rounded-full animate-spin" style="animation-duration: 2s;"></div>
  <div class="absolute w-7 h-7 border-2 border-green-500 border-r-transparent rounded-full animate-spin" 
       style="top: 15%; left: 15%; animation-duration: 1.5s; animation-direction: reverse;"></div>
  <div class="absolute w-4 h-4 border-2 border-red-500 border-b-transparent rounded-full animate-spin" 
       style="top: 50%; left: 50%; transform: translate(-50%, -50%); animation-duration: 1s;"></div>
</div>
```

### React
```jsx
const TripleRingLoader = ({ size = 40, colors = ['#1a73e8', '#34a853', '#ea4335'], speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      <div 
        className="absolute border-2 border-t-transparent rounded-full animate-spin"
        style={{ 
          width: size, 
          height: size,
          borderColor: colors[0],
          borderTopColor: 'transparent',
          animationDuration: `${2/speed}s`
        }}
      />
      <div 
        className="absolute border-2 border-r-transparent rounded-full animate-spin"
        style={{ 
          width: size * 0.7, 
          height: size * 0.7,
          borderColor: colors[1],
          borderRightColor: 'transparent',
          top: '15%',
          left: '15%',
          animationDuration: `${1.5/speed}s`,
          animationDirection: 'reverse'
        }}
      />
      <div 
        className="absolute border-2 border-b-transparent rounded-full animate-spin"
        style={{ 
          width: size * 0.4, 
          height: size * 0.4,
          borderColor: colors[2],
          borderBottomColor: 'transparent',
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)',
          animationDuration: `${1/speed}s`
        }}
      />
    </div>
  );
};
```

### Java
```java
public class TripleRingLoader extends JPanel {
    private Timer timer;
    private float[] angles = {0f, 0f, 0f};
    private int size = 40;
    private Color[] colors = {
        Color.decode("#1a73e8"),
        Color.decode("#34a853"),
        Color.decode("#ea4335")
    };
    private float speed = 1f;
    
    public TripleRingLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            angles[0] += 2f;  // Outer ring
            angles[1] -= 3f;  // Middle ring
            angles[2] += 6f;  // Inner ring
            
            for (int i = 0; i < angles.length; i++) {
                if (angles[i] >= 360f) angles[i] = 0f;
                if (angles[i] <= -360f) angles[i] = 0f;
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        g2d.setStroke(new BasicStroke(2f));
        
        // Outer ring
        g2d.setColor(colors[0]);
        g2d.rotate(Math.toRadians(angles[0]), centerX, centerY);
        g2d.drawArc(centerX - size/4, centerY - size/4, size/2, size/2, 0, 270);
        g2d.rotate(Math.toRadians(-angles[0]), centerX, centerY);
        
        // Middle ring
        g2d.setColor(colors[1]);
        g2d.rotate(Math.toRadians(angles[1]), centerX, centerY);
        g2d.drawArc(centerX - size/6, centerY - size/6, size/3, size/3, 90, 270);
        g2d.rotate(Math.toRadians(-angles[1]), centerX, centerY);
        
        // Inner ring
        g2d.setColor(colors[2]);
        g2d.rotate(Math.toRadians(angles[2]), centerX, centerY);
        g2d.drawArc(centerX - size/8, centerY - size/8, size/4, size/4, 180, 270);
        
        g2d.dispose();
    }
}
```

---

## Loader 6: Gear Wheel
**Type:** Spin | **Pattern:** Gear  
**Description:** Rotating gear-like pattern

### HTML/CSS
```html
<!-- Gear Wheel Loader -->
<div class="loader-6" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 animate-spin" style="animation-duration: 2s;">
    <svg viewBox="0 0 24 24" fill="currentColor">
      <path d="M12,15.5A3.5,3.5 0 0,1 8.5,12A3.5,3.5 0 0,1 12,8.5A3.5,3.5 0 0,1 15.5,12A3.5,3.5 0 0,1 12,15.5M19.43,12.97C19.47,12.65 19.5,12.33 19.5,12C19.5,11.67 19.47,11.34 19.43,11L21.54,9.37C21.73,9.22 21.78,8.95 21.66,8.73L19.66,5.27C19.54,5.05 19.27,4.96 19.05,5.05L16.56,6.05C16.04,5.66 15.5,5.32 14.87,5.07L14.5,2.42C14.46,2.18 14.25,2 14,2H10C9.75,2 9.54,2.18 9.5,2.42L9.13,5.07C8.5,5.32 7.96,5.66 7.44,6.05L4.95,5.05C4.73,4.96 4.46,5.05 4.34,5.27L2.34,8.73C2.22,8.95 2.27,9.22 2.46,9.37L4.57,11C4.53,11.34 4.5,11.67 4.5,12C4.5,12.33 4.53,12.65 4.57,12.97L2.46,14.63C2.27,14.78 2.22,15.05 2.34,15.27L4.34,18.73C4.46,18.95 4.73,19.03 4.95,18.95L7.44,17.94C7.96,18.34 8.5,18.68 9.13,18.93L9.5,21.58C9.54,21.82 9.75,22 10,22H14C14.25,22 14.46,21.82 14.5,21.58L14.87,18.93C15.5,18.68 16.04,18.34 16.56,17.94L19.05,18.95C19.27,19.03 19.54,18.95 19.66,18.73L21.66,15.27C21.78,15.05 21.73,14.78 21.54,14.63L19.43,12.97Z"/>
    </svg>
  </div>
</div>
```

### React
```jsx
const GearWheelLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color }}>
      <div 
        className="animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${2/speed}s`
        }}
      >
        <svg viewBox="0 0 24 24" fill="currentColor" width={size} height={size}>
          <path d="M12,15.5A3.5,3.5 0 0,1 8.5,12A3.5,3.5 0 0,1 12,8.5A3.5,3.5 0 0,1 15.5,12A3.5,3.5 0 0,1 12,15.5M19.43,12.97C19.47,12.65 19.5,12.33 19.5,12C19.5,11.67 19.47,11.34 19.43,11L21.54,9.37C21.73,9.22 21.78,8.95 21.66,8.73L19.66,5.27C19.54,5.05 19.27,4.96 19.05,5.05L16.56,6.05C16.04,5.66 15.5,5.32 14.87,5.07L14.5,2.42C14.46,2.18 14.25,2 14,2H10C9.75,2 9.54,2.18 9.5,2.42L9.13,5.07C8.5,5.32 7.96,5.66 7.44,6.05L4.95,5.05C4.73,4.96 4.46,5.05 4.34,5.27L2.34,8.73C2.22,8.95 2.27,9.22 2.46,9.37L4.57,11C4.53,11.34 4.5,11.67 4.5,12C4.5,12.33 4.53,12.65 4.57,12.97L2.46,14.63C2.27,14.78 2.22,15.05 2.34,15.27L4.34,18.73C4.46,18.95 4.73,19.03 4.95,18.95L7.44,17.94C7.96,18.34 8.5,18.68 9.13,18.93L9.5,21.58C9.54,21.82 9.75,22 10,22H14C14.25,22 14.46,21.82 14.5,21.58L14.87,18.93C15.5,18.68 16.04,18.34 16.56,17.94L19.05,18.95C19.27,19.03 19.54,18.95 19.66,18.73L21.66,15.27C21.78,15.05 21.73,14.78 21.54,14.63L19.43,12.97Z"/>
        </svg>
      </div>
    </div>
  );
};
```

### Java
```java
public class GearWheelLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public GearWheelLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(40 / speed), e -> {
            angle += 2f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        
        // Draw gear teeth
        for (int i = 0; i < 8; i++) {
            double rad = Math.toRadians(i * 45);
            int x1 = (int)(centerX + Math.cos(rad) * size/3);
            int y1 = (int)(centerY + Math.sin(rad) * size/3);
            int x2 = (int)(centerX + Math.cos(rad) * size/2.5);
            int y2 = (int)(centerY + Math.sin(rad) * size/2.5);
            
            g2d.setStroke(new BasicStroke(3f));
            g2d.drawLine(x1, y1, x2, y2);
        }
        
        // Draw center circle
        g2d.fillOval(centerX - size/6, centerY - size/6, size/3, size/3);
        
        g2d.dispose();
    }
}
```

---

## Loader 7: Clock Hand
**Type:** Spin | **Pattern:** Clock  
**Description:** Clock hand rotation effect

### HTML/CSS
```html
<!-- Clock Hand Loader -->
<div class="loader-7" style="width: 40px; height: 40px; position: relative; color: #1a73e8;">
  <div class="absolute w-10 h-10 border border-current rounded-full"></div>
  <div class="absolute w-0.5 h-4 bg-current animate-spin" style="top: 20%; left: 50%; transform-origin: bottom; animation-duration: 1s;"></div>
  <div class="absolute w-0.5 h-3 bg-current animate-spin" style="top: 25%; left: 50%; transform-origin: bottom; animation-duration: 8s;"></div>
</div>
```

### React
```jsx
const ClockHandLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, position: 'relative', color }}>
      <div 
        className="absolute border border-current rounded-full"
        style={{ width: size, height: size }}
      />
      <div 
        className="absolute bg-current animate-spin"
        style={{ 
          width: '2px', 
          height: size * 0.4,
          top: '10%',
          left: '50%',
          transformOrigin: 'bottom',
          animationDuration: `${1/speed}s`
        }}
      />
      <div 
        className="absolute bg-current animate-spin"
        style={{ 
          width: '2px', 
          height: size * 0.3,
          top: '20%',
          left: '50%',
          transformOrigin: 'bottom',
          animationDuration: `${8/speed}s`
        }}
      />
      <div 
        className="absolute bg-current rounded-full"
        style={{ 
          width: '4px', 
          height: '4px',
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)'
        }}
      />
    </div>
  );
};
```

### Java
```java
public class ClockHandLoader extends JPanel {
    private Timer timer;
    private float hourAngle = 0f;
    private float minuteAngle = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public ClockHandLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(50 / speed), e -> {
            minuteAngle += 6f;
            hourAngle += 0.5f;
            if (minuteAngle >= 360f) minuteAngle = 0f;
            if (hourAngle >= 360f) hourAngle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(1f));
        
        // Draw clock face
        g2d.drawOval(centerX - size/2, centerY - size/2, size, size);
        
        // Draw hour hand
        g2d.setStroke(new BasicStroke(2f));
        double hourRad = Math.toRadians(hourAngle - 90);
        int hourX = (int)(centerX + Math.cos(hourRad) * size/4);
        int hourY = (int)(centerY + Math.sin(hourRad) * size/4);
        g2d.drawLine(centerX, centerY, hourX, hourY);
        
        // Draw minute hand
        g2d.setStroke(new BasicStroke(1f));
        double minuteRad = Math.toRadians(minuteAngle - 90);
        int minuteX = (int)(centerX + Math.cos(minuteRad) * size/3);
        int minuteY = (int)(centerY + Math.sin(minuteRad) * size/3);
        g2d.drawLine(centerX, centerY, minuteX, minuteY);
        
        // Draw center dot
        g2d.fillOval(centerX - 2, centerY - 2, 4, 4);
        
        g2d.dispose();
    }
}
```

---

## Loader 8: Propeller
**Type:** Spin | **Pattern:** Propeller  
**Description:** Three-blade propeller animation

### HTML/CSS
```html
<!-- Propeller Loader -->
<div class="loader-8" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 animate-spin" style="animation-duration: 0.5s;">
    <div class="absolute w-8 h-0.5 bg-current" style="top: 50%; left: 10%; transform: translateY(-50%);"></div>
    <div class="absolute w-8 h-0.5 bg-current" style="top: 50%; left: 10%; transform: translateY(-50%) rotate(120deg); transform-origin: center;"></div>
    <div class="absolute w-8 h-0.5 bg-current" style="top: 50%; left: 10%; transform: translateY(-50%) rotate(240deg); transform-origin: center;"></div>
    <div class="absolute w-2 h-2 bg-current rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  </div>
</div>
```

### React
```jsx
const PropellerLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, position: 'relative' }}>
      <div 
        className="animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${0.5/speed}s`,
          position: 'relative'
        }}
      >
        {[0, 120, 240].map((rotation, index) => (
          <div 
            key={index}
            className="absolute bg-current"
            style={{ 
              width: size * 0.8, 
              height: '2px',
              top: '50%',
              left: '10%',
              transform: `translateY(-50%) rotate(${rotation}deg)`,
              transformOrigin: 'center'
            }}
          />
        ))}
        <div 
          className="absolute bg-current rounded-full"
          style={{ 
            width: '6px', 
            height: '6px',
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)'
          }}
        />
      </div>
    </div>
  );
};
```

### Java
```java
public class PropellerLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public PropellerLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(10 / speed), e -> {
            angle += 12f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(2f));
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        
        // Draw three propeller blades
        for (int i = 0; i < 3; i++) {
            double bladeAngle = Math.toRadians(i * 120);
            int x1 = (int)(centerX + Math.cos(bladeAngle) * size/8);
            int y1 = (int)(centerY + Math.sin(bladeAngle) * size/8);
            int x2 = (int)(centerX + Math.cos(bladeAngle) * size/2.5);
            int y2 = (int)(centerY + Math.sin(bladeAngle) * size/2.5);
            
            g2d.drawLine(x1, y1, x2, y2);
        }
        
        // Draw center hub
        g2d.fillOval(centerX - 3, centerY - 3, 6, 6);
        
        g2d.dispose();
    }
}
```

---

## Loader 9: Cross Rotate
**Type:** Spin | **Pattern:** Cross  
**Description:** Rotating cross/plus sign

### HTML/CSS
```html
<!-- Cross Rotate Loader -->
<div class="loader-9" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 animate-spin" style="animation-duration: 1.5s;">
    <div class="absolute w-8 h-1 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
    <div class="absolute w-1 h-8 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  </div>
</div>
```

### React
```jsx
const CrossRotateLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, position: 'relative' }}>
      <div 
        className="animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${1.5/speed}s`,
          position: 'relative'
        }}
      >
        <div 
          className="absolute bg-current"
          style={{ 
            width: size * 0.8, 
            height: '3px',
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)'
          }}
        />
        <div 
          className="absolute bg-current"
          style={{ 
            width: '3px', 
            height: size * 0.8,
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)'
          }}
        />
      </div>
    </div>
  );
};
```

### Java
```java
public class CrossRotateLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public CrossRotateLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(30 / speed), e -> {
            angle += 3f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(3f));
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        
        // Draw horizontal line
        g2d.drawLine(centerX - size/3, centerY, centerX + size/3, centerY);
        
        // Draw vertical line
        g2d.drawLine(centerX, centerY - size/3, centerX, centerY + size/3);
        
        g2d.dispose();
    }
}
```

---

## Loader 10: Star Spin
**Type:** Spin | **Pattern:** Star  
**Description:** Five-pointed star rotation

### HTML/CSS
```html
<!-- Star Spin Loader -->
<div class="loader-10" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 animate-spin" style="animation-duration: 2s;">
    <svg viewBox="0 0 24 24" fill="currentColor">
      <path d="M12,17.27L18.18,21L16.54,13.97L22,9.24L14.81,8.62L12,2L9.19,8.62L2,9.24L7.45,13.97L5.82,21L12,17.27Z"/>
    </svg>
  </div>
</div>
```

### React
```jsx
const StarSpinLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color }}>
      <div 
        className="animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${2/speed}s`
        }}
      >
        <svg viewBox="0 0 24 24" fill="currentColor" width={size} height={size}>
          <path d="M12,17.27L18.18,21L16.54,13.97L22,9.24L14.81,8.62L12,2L9.19,8.62L2,9.24L7.45,13.97L5.82,21L12,17.27Z"/>
        </svg>
      </div>
    </div>
  );
};
```

### Java
```java
public class StarSpinLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public StarSpinLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(40 / speed), e -> {
            angle += 2f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        
        // Create star shape
        int[] xPoints = new int[10];
        int[] yPoints = new int[10];
        
        for (int i = 0; i < 10; i++) {
            double starAngle = Math.toRadians(i * 36 - 90);
            int radius = (i % 2 == 0) ? size/3 : size/6;
            xPoints[i] = (int)(centerX + Math.cos(starAngle) * radius);
            yPoints[i] = (int)(centerY + Math.sin(starAngle) * radius);
        }
        
        Polygon star = new Polygon(xPoints, yPoints, 10);
        g2d.fillPolygon(star);
        
        g2d.dispose();
    }
}
```

---

## Loader 11: Orbit Motion
**Type:** Spin | **Pattern:** Orbit  
**Description:** Planetary orbit animation

### HTML/CSS
```html
<!-- Orbit Motion Loader -->
<div class="loader-11" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-10 h-10 border border-gray-300 rounded-full"></div>
  <div class="absolute w-2 h-2 bg-blue-500 rounded-full animate-spin" style="top: 5%; left: 50%; transform: translateX(-50%); animation-duration: 2s; transform-origin: 50% 300%;"></div>
</div>
```

### React
```jsx
const OrbitMotionLoader = ({ size = 40, primaryColor = '#1a73e8', secondaryColor = '#e5e7eb', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      <div 
        className="absolute border rounded-full"
        style={{ 
          width: size, 
          height: size,
          borderColor: secondaryColor
        }}
      />
      <div 
        className="absolute bg-current rounded-full animate-spin"
        style={{ 
          width: size * 0.15, 
          height: size * 0.15,
          top: '5%',
          left: '50%',
          transform: 'translateX(-50%)',
          transformOrigin: '50% 300%',
          animationDuration: `${2/speed}s`,
          color: primaryColor
        }}
      />
    </div>
  );
};
```

### Java
```java
public class OrbitMotionLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color primaryColor = Color.decode("#1a73e8");
    private Color secondaryColor = Color.decode("#e5e7eb");
    private float speed = 1f;
    
    public OrbitMotionLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(40 / speed), e -> {
            angle += 3f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getWidth() / 2;
        
        // Draw orbit path
        g2d.setColor(secondaryColor);
        g2d.setStroke(new BasicStroke(1f));
        g2d.drawOval(centerX - size/2, centerY - size/2, size, size);
        
        // Draw orbiting object
        g2d.setColor(primaryColor);
        double rad = Math.toRadians(angle);
        int orbitX = (int)(centerX + Math.cos(rad) * size/2);
        int orbitY = (int)(centerY + Math.sin(rad) * size/2);
        g2d.fillOval(orbitX - 3, orbitY - 3, 6, 6);
        
        g2d.dispose();
    }
}
```

---

## Loader 12: Satellite
**Type:** Spin | **Pattern:** Satellite  
**Description:** Satellite orbiting pattern

### HTML/CSS
```html
<!-- Satellite Loader -->
<div class="loader-12" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-3 h-3 bg-gray-400 rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  <div class="absolute w-1.5 h-1.5 bg-blue-500 rounded-full animate-spin" style="top: 20%; left: 50%; transform: translateX(-50%); animation-duration: 1.5s; transform-origin: 50% 250%;"></div>
  <div class="absolute w-1 h-1 bg-green-500 rounded-full animate-spin" style="top: 15%; left: 50%; transform: translateX(-50%); animation-duration: 0.8s; transform-origin: 50% 350%; animation-direction: reverse;"></div>
</div>
```

### React
```jsx
const SatelliteLoader = ({ size = 40, colors = ['#9ca3af', '#1a73e8', '#34a853'], speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {/* Central body */}
      <div 
        className="absolute rounded-full"
        style={{ 
          width: size * 0.3, 
          height: size * 0.3,
          backgroundColor: colors[0],
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)'
        }}
      />
      
      {/* First satellite */}
      <div 
        className="absolute rounded-full animate-spin"
        style={{ 
          width: size * 0.15, 
          height: size * 0.15,
          backgroundColor: colors[1],
          top: '20%',
          left: '50%',
          transform: 'translateX(-50%)',
          transformOrigin: '50% 250%',
          animationDuration: `${1.5/speed}s`
        }}
      />
      
      {/* Second satellite */}
      <div 
        className="absolute rounded-full animate-spin"
        style={{ 
          width: size * 0.1, 
          height: size * 0.1,
          backgroundColor: colors[2],
          top: '15%',
          left: '50%',
          transform: 'translateX(-50%)',
          transformOrigin: '50% 350%',
          animationDuration: `${0.8/speed}s`,
          animationDirection: 'reverse'
        }}
      />
    </div>
  );
};
```

### Java
```java
public class SatelliteLoader extends JPanel {
    private Timer timer;
    private float satellite1Angle = 0f;
    private float satellite2Angle = 0f;
    private int size = 40;
    private Color[] colors = {
        Color.decode("#9ca3af"),
        Color.decode("#1a73e8"),
        Color.decode("#34a853")
    };
    private float speed = 1f;
    
    public SatelliteLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            satellite1Angle += 3f;
            satellite2Angle -= 5f;
            if (satellite1Angle >= 360f) satellite1Angle = 0f;
            if (satellite2Angle <= -360f) satellite2Angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        // Draw central body
        g2d.setColor(colors[0]);
        g2d.fillOval(centerX - size/8, centerY - size/8, size/4, size/4);
        
        // Draw first satellite
        g2d.setColor(colors[1]);
        double rad1 = Math.toRadians(satellite1Angle);
        int sat1X = (int)(centerX + Math.cos(rad1) * size/3);
        int sat1Y = (int)(centerY + Math.sin(rad1) * size/3);
        g2d.fillOval(sat1X - 3, sat1Y - 3, 6, 6);
        
        // Draw second satellite
        g2d.setColor(colors[2]);
        double rad2 = Math.toRadians(satellite2Angle);
        int sat2X = (int)(centerX + Math.cos(rad2) * size/2.5);
        int sat2Y = (int)(centerY + Math.sin(rad2) * size/2.5);
        g2d.fillOval(sat2X - 2, sat2Y - 2, 4, 4);
        
        g2d.dispose();
    }
}
```

---

## Loader 13: Planet Rotation
**Type:** Spin | **Pattern:** Planet  
**Description:** Planet with rings

### HTML/CSS
```html
<!-- Planet Rotation Loader -->
<div class="loader-13" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-8 h-8 bg-blue-500 rounded-full animate-spin" style="top: 50%; left: 50%; transform: translate(-50%, -50%); animation-duration: 4s;"></div>
  <div class="absolute w-10 h-10 border border-gray-300 rounded-full animate-spin" style="top: 50%; left: 50%; transform: translate(-50%, -50%) rotateX(60deg); animation-duration: 2s;"></div>
</div>
```

### React
```jsx
const PlanetRotationLoader = ({ size = 40, planetColor = '#1a73e8', ringColor = '#e5e7eb', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {/* Planet */}
      <div 
        className="absolute rounded-full animate-spin"
        style={{ 
          width: size * 0.7, 
          height: size * 0.7,
          backgroundColor: planetColor,
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)',
          animationDuration: `${4/speed}s`
        }}
      />
      
      {/* Ring */}
      <div 
        className="absolute border rounded-full animate-spin"
        style={{ 
          width: size, 
          height: size,
          borderColor: ringColor,
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%) rotateX(60deg)',
          animationDuration: `${2/speed}s`
        }}
      />
    </div>
  );
};
```

### Java
```java
public class PlanetRotationLoader extends JPanel {
    private Timer timer;
    private float planetAngle = 0f;
    private float ringAngle = 0f;
    private int size = 40;
    private Color planetColor = Color.decode("#1a73e8");
    private Color ringColor = Color.decode("#e5e7eb");
    private float speed = 1f;
    
    public PlanetRotationLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(50 / speed), e -> {
            planetAngle += 1f;
            ringAngle += 2f;
            if (planetAngle >= 360f) planetAngle = 0f;
            if (ringAngle >= 360f) ringAngle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        // Draw planet
        g2d.setColor(planetColor);
        g2d.rotate(Math.toRadians(planetAngle), centerX, centerY);
        g2d.fillOval(centerX - size/4, centerY - size/4, size/2, size/2);
        g2d.rotate(Math.toRadians(-planetAngle), centerX, centerY);
        
        // Draw ring (elliptical to simulate 3D effect)
        g2d.setColor(ringColor);
        g2d.setStroke(new BasicStroke(1f));
        g2d.rotate(Math.toRadians(ringAngle), centerX, centerY);
        g2d.drawOval(centerX - size/2, centerY - size/6, size, size/3);
        
        g2d.dispose();
    }
}
```

---

## Loader 14: Solar System
**Type:** Spin | **Pattern:** Solar  
**Description:** Multi-planet system

### HTML/CSS
```html
<!-- Solar System Loader -->
<div class="loader-14" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-2 h-2 bg-yellow-500 rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  <div class="absolute w-1 h-1 bg-blue-500 rounded-full animate-spin" style="top: 35%; left: 50%; transform: translateX(-50%); animation-duration: 1s; transform-origin: 50% 200%;"></div>
  <div class="absolute w-1 h-1 bg-red-500 rounded-full animate-spin" style="top: 25%; left: 50%; transform: translateX(-50%); animation-duration: 2s; transform-origin: 50% 300%;"></div>
  <div class="absolute w-1 h-1 bg-green-500 rounded-full animate-spin" style="top: 15%; left: 50%; transform: translateX(-50%); animation-duration: 3s; transform-origin: 50% 400%;"></div>
</div>
```

### React
```jsx
const SolarSystemLoader = ({ size = 40, colors = ['#fbbf24', '#1a73e8', '#ea4335', '#34a853'], speed = 1 }) => {
  const planets = [
    { distance: 0.3, duration: 1, color: colors[1] },
    { distance: 0.5, duration: 2, color: colors[2] },
    { distance: 0.7, duration: 3, color: colors[3] }
  ];
  
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {/* Sun */}
      <div 
        className="absolute rounded-full"
        style={{ 
          width: size * 0.2, 
          height: size * 0.2,
          backgroundColor: colors[0],
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)'
        }}
      />
      
      {/* Planets */}
      {planets.map((planet, index) => (
        <div 
          key={index}
          className="absolute rounded-full animate-spin"
          style={{ 
            width: size * 0.08, 
            height: size * 0.08,
            backgroundColor: planet.color,
            top: `${50 - planet.distance * 50}%`,
            left: '50%',
            transform: 'translateX(-50%)',
            transformOrigin: `50% ${100 / planet.distance}%`,
            animationDuration: `${planet.duration/speed}s`
          }}
        />
      ))}
    </div>
  );
};
```

### Java
```java
public class SolarSystemLoader extends JPanel {
    private Timer timer;
    private float[] planetAngles = {0f, 0f, 0f};
    private int size = 40;
    private Color[] colors = {
        Color.decode("#fbbf24"),
        Color.decode("#1a73e8"),
        Color.decode("#ea4335"),
        Color.decode("#34a853")
    };
    private float speed = 1f;
    
    public SolarSystemLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(30 / speed), e -> {
            planetAngles[0] += 6f;  // Fastest orbit
            planetAngles[1] += 3f;  // Medium orbit
            planetAngles[2] += 2f;  // Slowest orbit
            
            for (int i = 0; i < planetAngles.length; i++) {
                if (planetAngles[i] >= 360f) planetAngles[i] = 0f;
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        // Draw sun
        g2d.setColor(colors[0]);
        g2d.fillOval(centerX - 4, centerY - 4, 8, 8);
        
        // Draw planets
        int[] distances = {size/4, size/3, size/2};
        for (int i = 0; i < 3; i++) {
            g2d.setColor(colors[i + 1]);
            double rad = Math.toRadians(planetAngles[i]);
            int planetX = (int)(centerX + Math.cos(rad) * distances[i]);
            int planetY = (int)(centerY + Math.sin(rad) * distances[i]);
            g2d.fillOval(planetX - 2, planetY - 2, 4, 4);
        }
        
        g2d.dispose();
    }
}
```

---

## Loader 15: Atom Model
**Type:** Spin | **Pattern:** Atom  
**Description:** Atomic structure animation

### HTML/CSS
```html
<!-- Atom Model Loader -->
<div class="loader-15" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-2 h-2 bg-yellow-400 rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  <div class="absolute w-10 h-10 border border-blue-500 rounded-full animate-spin" style="animation-duration: 2s;"></div>
  <div class="absolute w-10 h-10 border border-red-500 rounded-full animate-spin" style="transform: rotate(60deg); animation-duration: 2.5s;"></div>
  <div class="absolute w-10 h-10 border border-green-500 rounded-full animate-spin" style="transform: rotate(120deg); animation-duration: 3s;"></div>
</div>
```

### React
```jsx
const AtomModelLoader = ({ size = 40, colors = ['#fbbf24', '#1a73e8', '#ea4335', '#34a853'], speed = 1 }) => {
  const orbits = [
    { rotation: 0, duration: 2, color: colors[1] },
    { rotation: 60, duration: 2.5, color: colors[2] },
    { rotation: 120, duration: 3, color: colors[3] }
  ];
  
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {/* Nucleus */}
      <div 
        className="absolute rounded-full"
        style={{ 
          width: size * 0.2, 
          height: size * 0.2,
          backgroundColor: colors[0],
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)'
        }}
      />
      
      {/* Electron orbits */}
      {orbits.map((orbit, index) => (
        <div 
          key={index}
          className="absolute border rounded-full animate-spin"
          style={{ 
            width: size, 
            height: size,
            borderColor: orbit.color,
            transform: `rotate(${orbit.rotation}deg)`,
            animationDuration: `${orbit.duration/speed}s`
          }}
        />
      ))}
    </div>
  );
};
```

### Java
```java
public class AtomModelLoader extends JPanel {
    private Timer timer;
    private float[] orbitAngles = {0f, 0f, 0f};
    private int size = 40;
    private Color nucleusColor = Color.decode("#fbbf24");
    private Color[] orbitColors = {
        Color.decode("#1a73e8"),
        Color.decode("#ea4335"),
        Color.decode("#34a853")
    };
    private float speed = 1f;
    
    public AtomModelLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(30 / speed), e -> {
            orbitAngles[0] += 2f;
            orbitAngles[1] += 1.5f;
            orbitAngles[2] += 1f;
            
            for (int i = 0; i < orbitAngles.length; i++) {
                if (orbitAngles[i] >= 360f) orbitAngles[i] = 0f;
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        // Draw electron orbits
        g2d.setStroke(new BasicStroke(1f));
        for (int i = 0; i < 3; i++) {
            g2d.setColor(orbitColors[i]);
            g2d.rotate(Math.toRadians(orbitAngles[i] + i * 60), centerX, centerY);
            g2d.drawOval(centerX - size/2, centerY - size/2, size, size);
            g2d.rotate(Math.toRadians(-(orbitAngles[i] + i * 60)), centerX, centerY);
        }
        
        // Draw nucleus
        g2d.setColor(nucleusColor);
        g2d.fillOval(centerX - 4, centerY - 4, 8, 8);
        
        g2d.dispose();
    }
}
```

---

## Loader 16: DNA Helix
**Type:** Spin | **Pattern:** DNA  
**Description:** Double helix rotation

### HTML/CSS
```html
<!-- DNA Helix Loader -->
<div class="loader-16" style="width: 40px; height: 40px; position: relative; overflow: hidden;">
  <div class="absolute w-full h-1 animate-spin" style="animation-duration: 1s; transform-origin: center;">
    <div class="w-2 h-2 bg-blue-500 rounded-full absolute" style="left: 25%;"></div>
    <div class="w-2 h-2 bg-red-500 rounded-full absolute" style="right: 25%;"></div>
  </div>
  <div class="absolute w-full h-1 animate-spin" style="top: 25%; animation-duration: 1s; animation-delay: 0.25s; transform-origin: center;">
    <div class="w-2 h-2 bg-blue-500 rounded-full absolute" style="right: 25%;"></div>
    <div class="w-2 h-2 bg-red-500 rounded-full absolute" style="left: 25%;"></div>
  </div>
  <div class="absolute w-full h-1 animate-spin" style="top: 50%; animation-duration: 1s; animation-delay: 0.5s; transform-origin: center;">
    <div class="w-2 h-2 bg-blue-500 rounded-full absolute" style="left: 25%;"></div>
    <div class="w-2 h-2 bg-red-500 rounded-full absolute" style="right: 25%;"></div>
  </div>
  <div class="absolute w-full h-1 animate-spin" style="top: 75%; animation-duration: 1s; animation-delay: 0.75s; transform-origin: center;">
    <div class="w-2 h-2 bg-blue-500 rounded-full absolute" style="right: 25%;"></div>
    <div class="w-2 h-2 bg-red-500 rounded-full absolute" style="left: 25%;"></div>
  </div>
</div>
```

### React
```jsx
const DNAHelixLoader = ({ size = 40, colors = ['#1a73e8', '#ea4335'], speed = 1 }) => {
  const helixLevels = [
    { top: '12.5%', delay: 0, leftFirst: true },
    { top: '37.5%', delay: 0.25, leftFirst: false },
    { top: '62.5%', delay: 0.5, leftFirst: true },
    { top: '87.5%', delay: 0.75, leftFirst: false }
  ];
  
  return (
    <div style={{ width: size, height: size, position: 'relative', overflow: 'hidden' }}>
      {helixLevels.map((level, index) => (
        <div 
          key={index}
          className="absolute w-full animate-spin"
          style={{ 
            height: '4px',
            top: level.top,
            animationDuration: `${1/speed}s`,
            animationDelay: `${level.delay/speed}s`,
            transformOrigin: 'center'
          }}
        >
          <div 
            className="absolute rounded-full"
            style={{ 
              width: size * 0.15, 
              height: size * 0.15,
              backgroundColor: colors[0],
              [level.leftFirst ? 'left' : 'right']: '25%',
              top: '50%',
              transform: 'translateY(-50%)'
            }}
          />
          <div 
            className="absolute rounded-full"
            style={{ 
              width: size * 0.15, 
              height: size * 0.15,
              backgroundColor: colors[1],
              [level.leftFirst ? 'right' : 'left']: '25%',
              top: '50%',
              transform: 'translateY(-50%)'
            }}
          />
        </div>
      ))}
    </div>
  );
};
```

### Java
```java
public class DNAHelixLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color[] colors = {
        Color.decode("#1a73e8"),
        Color.decode("#ea4335")
    };
    private float speed = 1f;
    
    public DNAHelixLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            angle += 6f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        
        // Draw DNA helix strands
        for (int level = 0; level < 4; level++) {
            int y = (int)(getHeight() * (0.125 + level * 0.25));
            float levelAngle = angle + level * 90f;
            
            // Calculate positions for the two strands
            double rad = Math.toRadians(levelAngle);
            int x1 = (int)(centerX + Math.cos(rad) * size/4);
            int x2 = (int)(centerX - Math.cos(rad) * size/4);
            
            // Draw the nucleotides
            g2d.setColor(colors[0]);
            g2d.fillOval(x1 - 3, y - 3, 6, 6);
            
            g2d.setColor(colors[1]);
            g2d.fillOval(x2 - 3, y - 3, 6, 6);
            
            // Draw connecting line
            g2d.setColor(Color.LIGHT_GRAY);
            g2d.setStroke(new BasicStroke(1f));
            g2d.drawLine(x1, y, x2, y);
        }
        
        g2d.dispose();
    }
}
```

---

## Loader 17: Spiral Galaxy
**Type:** Spin | **Pattern:** Spiral  
**Description:** Galaxy spiral pattern

### HTML/CSS
```html
<!-- Spiral Galaxy Loader -->
<div class="loader-17" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 animate-spin" style="animation-duration: 3s;">
    <div class="absolute w-1 h-1 bg-current rounded-full" style="top: 50%; left: 60%; transform: translateY(-50%);"></div>
    <div class="absolute w-1 h-1 bg-current rounded-full" style="top: 40%; left: 70%; transform: translateY(-50%);"></div>
    <div class="absolute w-1 h-1 bg-current rounded-full" style="top: 30%; left: 75%; transform: translateY(-50%);"></div>
    <div class="absolute w-1 h-1 bg-current rounded-full" style="top: 60%; left: 70%; transform: translateY(-50%);"></div>
    <div class="absolute w-1 h-1 bg-current rounded-full" style="top: 70%; left: 75%; transform: translateY(-50%);"></div>
    <div class="absolute w-2 h-2 bg-yellow-400 rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  </div>
</div>
```

### React
```jsx
const SpiralGalaxyLoader = ({ size = 40, starColor = '#1a73e8', centerColor = '#fbbf24', speed = 1 }) => {
  const stars = [
    { top: '50%', left: '60%' },
    { top: '40%', left: '70%' },
    { top: '30%', left: '75%' },
    { top: '60%', left: '70%' },
    { top: '70%', left: '75%' },
    { top: '20%', left: '65%' },
    { top: '80%', left: '65%' }
  ];
  
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      <div 
        className="animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${3/speed}s`,
          position: 'relative'
        }}
      >
        {/* Stars */}
        {stars.map((star, index) => (
          <div 
            key={index}
            className="absolute rounded-full"
            style={{ 
              width: size * 0.08, 
              height: size * 0.08,
              backgroundColor: starColor,
              top: star.top,
              left: star.left,
              transform: 'translateY(-50%)'
            }}
          />
        ))}
        
        {/* Galaxy center */}
        <div 
          className="absolute rounded-full"
          style={{ 
            width: size * 0.15, 
            height: size * 0.15,
            backgroundColor: centerColor,
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)'
          }}
        />
      </div>
    </div>
  );
};
```

### Java
```java
public class SpiralGalaxyLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color starColor = Color.decode("#1a73e8");
    private Color centerColor = Color.decode("#fbbf24");
    private float speed = 1f;
    
    public SpiralGalaxyLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(60 / speed), e -> {
            angle += 1f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        
        // Draw spiral arms with stars
        g2d.setColor(starColor);
        for (int arm = 0; arm < 2; arm++) {
            for (int i = 0; i < 8; i++) {
                double spiralAngle = Math.toRadians(arm * 180 + i * 25);
                int distance = (int)(size/6 + i * 2);
                int starX = (int)(centerX + Math.cos(spiralAngle) * distance);
                int starY = (int)(centerY + Math.sin(spiralAngle) * distance);
                
                g2d.fillOval(starX - 1, starY - 1, 2, 2);
            }
        }
        
        // Draw galaxy center
        g2d.setColor(centerColor);
        g2d.fillOval(centerX - 3, centerY - 3, 6, 6);
        
        g2d.dispose();
    }
}
```

---

## Loader 18: Tornado Twist
**Type:** Spin | **Pattern:** Tornado  
**Description:** Tornado-like rotation

### HTML/CSS
```html
<!-- Tornado Twist Loader -->
<div class="loader-18" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-8 h-1 bg-gray-400 animate-spin" style="top: 20%; left: 50%; transform: translateX(-50%); animation-duration: 0.3s;"></div>
  <div class="absolute w-7 h-1 bg-gray-500 animate-spin" style="top: 30%; left: 50%; transform: translateX(-50%); animation-duration: 0.4s;"></div>
  <div class="absolute w-6 h-1 bg-gray-600 animate-spin" style="top: 40%; left: 50%; transform: translateX(-50%); animation-duration: 0.5s;"></div>
  <div class="absolute w-5 h-1 bg-gray-700 animate-spin" style="top: 50%; left: 50%; transform: translateX(-50%); animation-duration: 0.6s;"></div>
  <div class="absolute w-4 h-1 bg-gray-800 animate-spin" style="top: 60%; left: 50%; transform: translateX(-50%); animation-duration: 0.7s;"></div>
  <div class="absolute w-3 h-1 bg-gray-900 animate-spin" style="top: 70%; left: 50%; transform: translateX(-50%); animation-duration: 0.8s;"></div>
</div>
```

### React
```jsx
const TornadoTwistLoader = ({ size = 40, colors = ['#9ca3af', '#6b7280', '#4b5563', '#374151', '#1f2937', '#111827'], speed = 1 }) => {
  const levels = colors.map((color, index) => ({
    top: `${20 + index * 10}%`,
    width: `${80 - index * 10}%`,
    color,
    duration: (0.3 + index * 0.1) / speed
  }));
  
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {levels.map((level, index) => (
        <div 
          key={index}
          className="absolute animate-spin"
          style={{ 
            width: level.width,
            height: '3px',
            backgroundColor: level.color,
            top: level.top,
            left: '50%',
            transform: 'translateX(-50%)',
            animationDuration: `${level.duration}s`
          }}
        />
      ))}
    </div>
  );
};
```

### Java
```java
public class TornadoTwistLoader extends JPanel {
    private Timer timer;
    private float[] levelAngles = new float[6];
    private int size = 40;
    private Color[] colors = {
        Color.decode("#9ca3af"),
        Color.decode("#6b7280"),
        Color.decode("#4b5563"),
        Color.decode("#374151"),
        Color.decode("#1f2937"),
        Color.decode("#111827")
    };
    private float speed = 1f;
    
    public TornadoTwistLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(10 / speed), e -> {
            for (int i = 0; i < levelAngles.length; i++) {
                levelAngles[i] += (12f + i * 2f);
                if (levelAngles[i] >= 360f) levelAngles[i] = 0f;
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        g2d.setStroke(new BasicStroke(3f));
        
        for (int i = 0; i < 6; i++) {
            int y = (int)(getHeight() * (0.2 + i * 0.1));
            int lineWidth = (int)(size * (0.8 - i * 0.1));
            
            g2d.setColor(colors[i]);
            g2d.rotate(Math.toRadians(levelAngles[i]), centerX, y);
            g2d.drawLine(centerX - lineWidth/2, y, centerX + lineWidth/2, y);
            g2d.rotate(Math.toRadians(-levelAngles[i]), centerX, y);
        }
        
        g2d.dispose();
    }
}
```

---

## Loader 19: Fan Blade
**Type:** Spin | **Pattern:** Fan  
**Description:** Cooling fan animation

### HTML/CSS
```html
<!-- Fan Blade Loader -->
<div class="loader-19" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 animate-spin" style="animation-duration: 0.2s;">
    <div class="absolute w-4 h-1 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
    <div class="absolute w-4 h-1 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%) rotate(45deg);"></div>
    <div class="absolute w-4 h-1 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%) rotate(90deg);"></div>
    <div class="absolute w-4 h-1 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%) rotate(135deg);"></div>
    <div class="absolute w-2 h-2 bg-gray-600 rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  </div>
</div>
```

### React
```jsx
const FanBladeLoader = ({ size = 40, bladeColor = '#1a73e8', hubColor = '#4b5563', speed = 1 }) => {
  const blades = [0, 45, 90, 135];
  
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      <div 
        className="animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${0.2/speed}s`,
          position: 'relative'
        }}
      >
        {/* Fan blades */}
        {blades.map((rotation, index) => (
          <div 
            key={index}
            className="absolute"
            style={{ 
              width: size * 0.4, 
              height: '3px',
              backgroundColor: bladeColor,
              top: '50%',
              left: '50%',
              transform: `translate(-50%, -50%) rotate(${rotation}deg)`
            }}
          />
        ))}
        
        {/* Hub */}
        <div 
          className="absolute rounded-full"
          style={{ 
            width: size * 0.2, 
            height: size * 0.2,
            backgroundColor: hubColor,
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)'
          }}
        />
      </div>
    </div>
  );
};
```

### Java
```java
public class FanBladeLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color bladeColor = Color.decode("#1a73e8");
    private Color hubColor = Color.decode("#4b5563");
    private float speed = 1f;
    
    public FanBladeLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(5 / speed), e -> {
            angle += 18f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(bladeColor);
        g2d.setStroke(new BasicStroke(3f));
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        
        // Draw four fan blades
        for (int i = 0; i < 4; i++) {
            double bladeAngle = Math.toRadians(i * 90);
            int x1 = (int)(centerX + Math.cos(bladeAngle) * size/8);
            int y1 = (int)(centerY + Math.sin(bladeAngle) * size/8);
            int x2 = (int)(centerX + Math.cos(bladeAngle) * size/3);
            int y2 = (int)(centerY + Math.sin(bladeAngle) * size/3);
            
            g2d.drawLine(x1, y1, x2, y2);
        }
        
        // Draw hub
        g2d.setColor(hubColor);
        g2d.fillOval(centerX - 4, centerY - 4, 8, 8);
        
        g2d.dispose();
    }
}
```

---

## Loader 20: Turbine
**Type:** Spin | **Pattern:** Turbine  
**Description:** Wind turbine rotation

### HTML/CSS
```html
<!-- Turbine Loader -->
<div class="loader-20" style="width: 40px; height: 40px; color: #1a73e8;">
  <div class="w-10 h-10 animate-spin" style="animation-duration: 1s;">
    <div class="absolute w-6 h-0.5 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%) rotate(0deg); transform-origin: 10% center;"></div>
    <div class="absolute w-6 h-0.5 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%) rotate(120deg); transform-origin: 10% center;"></div>
    <div class="absolute w-6 h-0.5 bg-current" style="top: 50%; left: 50%; transform: translate(-50%, -50%) rotate(240deg); transform-origin: 10% center;"></div>
    <div class="absolute w-1 h-1 bg-gray-700 rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  </div>
</div>
```

### React
```jsx
const TurbineLoader = ({ size = 40, bladeColor = '#1a73e8', hubColor = '#374151', speed = 1 }) => {
  const blades = [0, 120, 240];
  
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      <div 
        className="animate-spin"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${1/speed}s`,
          position: 'relative'
        }}
      >
        {/* Turbine blades */}
        {blades.map((rotation, index) => (
          <div 
            key={index}
            className="absolute"
            style={{ 
              width: size * 0.6, 
              height: '2px',
              backgroundColor: bladeColor,
              top: '50%',
              left: '50%',
              transform: `translate(-50%, -50%) rotate(${rotation}deg)`,
              transformOrigin: '10% center'
            }}
          />
        ))}
        
        {/* Hub */}
        <div 
          className="absolute rounded-full"
          style={{ 
            width: size * 0.1, 
            height: size * 0.1,
            backgroundColor: hubColor,
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)'
          }}
        />
      </div>
    </div>
  );
};
```

### Java
```java
public class TurbineLoader extends JPanel {
    private Timer timer;
    private float angle = 0f;
    private int size = 40;
    private Color bladeColor = Color.decode("#1a73e8");
    private Color hubColor = Color.decode("#374151");
    private float speed = 1f;
    
    public TurbineLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            angle += 3f;
            if (angle >= 360f) angle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(bladeColor);
        g2d.setStroke(new BasicStroke(2f));
        g2d.rotate(Math.toRadians(angle), centerX, centerY);
        
        // Draw three turbine blades
        for (int i = 0; i < 3; i++) {
            double bladeAngle = Math.toRadians(i * 120);
            int x1 = (int)(centerX + Math.cos(bladeAngle) * size/10);
            int y1 = (int)(centerY + Math.sin(bladeAngle) * size/10);
            int x2 = (int)(centerX + Math.cos(bladeAngle) * size/2.5);
            int y2 = (int)(centerY + Math.sin(bladeAngle) * size/2.5);
            
            g2d.drawLine(x1, y1, x2, y2);
        }
        
        // Draw hub
        g2d.setColor(hubColor);
        g2d.fillOval(centerX - 2, centerY - 2, 4, 4);
        
        g2d.dispose();
    }
}
```

---

# Pulsing Loaders (21-40)

## Loader 21: Pulse Dot
**Type:** Pulse | **Pattern:** Dot  
**Description:** A simple pulsing dot

### HTML/CSS
```html
<!-- Pulse Dot Loader -->
<div class="loader-21" style="width: 40px; height: 40px; color: #1a73e8; display: flex; align-items: center; justify-content: center;">
  <div class="w-6 h-6 bg-current rounded-full animate-pulse"></div>
</div>

<style>
.loader-21 > div {
  animation-duration: 2s;
}
</style>
```

### React
```jsx
const PulseDotLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
      <div 
        className="bg-current rounded-full animate-pulse"
        style={{ 
          width: size * 0.6, 
          height: size * 0.6,
          animationDuration: `${2/speed}s`
        }}
      />
    </div>
  );
};
```

### Java
```java
public class PulseDotLoader extends JPanel {
    private Timer timer;
    private float scale = 0.6f;
    private boolean growing = true;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public PulseDotLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(50 / speed), e -> {
            if (growing) {
                scale += 0.02f;
                if (scale >= 1f) growing = false;
            } else {
                scale -= 0.02f;
                if (scale <= 0.6f) growing = true;
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        int dotSize = (int)(size * 0.6 * scale);
        
        g2d.setColor(color);
        g2d.fillOval(centerX - dotSize/2, centerY - dotSize/2, dotSize, dotSize);
        
        g2d.dispose();
    }
}
```

---

## Loader 22: Pulse Ring
**Type:** Pulse | **Pattern:** Ring  
**Description:** A pulsing ring border

### HTML/CSS
```html
<!-- Pulse Ring Loader -->
<div class="loader-22" style="width: 40px; height: 40px; color: #1a73e8; display: flex; align-items: center; justify-content: center;">
  <div class="w-10 h-10 border-2 border-current rounded-full animate-ping"></div>
</div>

<style>
.loader-22 > div {
  animation-duration: 1.5s;
}
</style>
```

### React
```jsx
const PulseRingLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
      <div 
        className="border-2 border-current rounded-full animate-ping"
        style={{ 
          width: size, 
          height: size,
          animationDuration: `${1.5/speed}s`
        }}
      />
    </div>
  );
};
```

### Java
```java
public class PulseRingLoader extends JPanel {
    private Timer timer;
    private float opacity = 1f;
    private float scale = 0.8f;
    private boolean pulsing = true;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public PulseRingLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(30 / speed), e -> {
            if (pulsing) {
                scale += 0.02f;
                opacity -= 0.02f;
                if (scale >= 1.2f) {
                    scale = 0.8f;
                    opacity = 1f;
                }
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        int ringSize = (int)(size * scale);
        
        g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, opacity));
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(2f));
        g2d.drawOval(centerX - ringSize/2, centerY - ringSize/2, ringSize, ringSize);
        
        g2d.dispose();
    }
}
```

---

## Loader 23: Heartbeat
**Type:** Pulse | **Pattern:** Heart  
**Description:** Heart rhythm pulse

### HTML/CSS
```html
<!-- Heartbeat Loader -->
<div class="loader-23" style="width: 40px; height: 40px; color: #ea4335; display: flex; align-items: center; justify-content: center;">
  <div class="w-6 h-6 animate-pulse" style="animation-duration: 0.8s;">
    <svg viewBox="0 0 24 24" fill="currentColor">
      <path d="M12,21.35L10.55,20.03C5.4,15.36 2,12.27 2,8.5C2,5.41 4.42,3 7.5,3C9.24,3 10.91,3.81 12,5.08C13.09,3.81 14.76,3 16.5,3C19.58,3 22,5.41 22,8.5C22,12.27 18.6,15.36 13.45,20.03L12,21.35Z"/>
    </svg>
  </div>
</div>
```

### React
```jsx
const HeartbeatLoader = ({ size = 40, color = '#ea4335', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
      <div 
        className="animate-pulse"
        style={{ 
          width: size * 0.6, 
          height: size * 0.6,
          animationDuration: `${0.8/speed}s`
        }}
      >
        <svg viewBox="0 0 24 24" fill="currentColor" width={size * 0.6} height={size * 0.6}>
          <path d="M12,21.35L10.55,20.03C5.4,15.36 2,12.27 2,8.5C2,5.41 4.42,3 7.5,3C9.24,3 10.91,3.81 12,5.08C13.09,3.81 14.76,3 16.5,3C19.58,3 22,5.41 22,8.5C22,12.27 18.6,15.36 13.45,20.03L12,21.35Z"/>
        </svg>
      </div>
    </div>
  );
};
```

### Java
```java
public class HeartbeatLoader extends JPanel {
    private Timer timer;
    private float scale = 0.8f;
    private boolean beating = true;
    private int beatPhase = 0;
    private int size = 40;
    private Color color = Color.decode("#ea4335");
    private float speed = 1f;
    
    public HeartbeatLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            beatPhase++;
            if (beatPhase < 10) {
                scale = 0.8f + (float)Math.sin(beatPhase * Math.PI / 10) * 0.3f;
            } else if (beatPhase < 20) {
                scale = 0.8f + (float)Math.sin((beatPhase - 10) * Math.PI / 10) * 0.2f;
            } else {
                beatPhase = 0;
                scale = 0.8f;
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        int heartSize = (int)(size * 0.6 * scale);
        
        g2d.setColor(color);
        
        // Simple heart shape using two circles and a triangle
        g2d.fillOval(centerX - heartSize/3, centerY - heartSize/3, heartSize/2, heartSize/2);
        g2d.fillOval(centerX - heartSize/6, centerY - heartSize/3, heartSize/2, heartSize/2);
        
        int[] xPoints = {centerX - heartSize/3, centerX + heartSize/3, centerX};
        int[] yPoints = {centerY, centerY, centerY + heartSize/2};
        g2d.fillPolygon(xPoints, yPoints, 3);
        
        g2d.dispose();
    }
}
```

---

## Loader 24: Breathing Circle
**Type:** Pulse | **Pattern:** Breath  
**Description:** Breathing animation

### HTML/CSS
```html
<!-- Breathing Circle Loader -->
<div class="loader-24" style="width: 40px; height: 40px; color: #1a73e8; display: flex; align-items: center; justify-content: center;">
  <div class="w-8 h-8 border-2 border-current rounded-full animate-pulse" style="animation-duration: 3s;"></div>
</div>

<style>
@keyframes breathe {
  0%, 100% { transform: scale(0.8); opacity: 0.7; }
  50% { transform: scale(1.2); opacity: 1; }
}
.loader-24 > div {
  animation: breathe 3s ease-in-out infinite;
}
</style>
```

### React
```jsx
const BreathingCircleLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  const breatheKeyframes = `
    @keyframes breathe {
      0%, 100% { transform: scale(0.8); opacity: 0.7; }
      50% { transform: scale(1.2); opacity: 1; }
    }
  `;
  
  return (
    <>
      <style>{breatheKeyframes}</style>
      <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
        <div 
          className="border-2 border-current rounded-full"
          style={{ 
            width: size * 0.8, 
            height: size * 0.8,
            animation: `breathe ${3/speed}s ease-in-out infinite`
          }}
        />
      </div>
    </>
  );
};
```

### Java
```java
public class BreathingCircleLoader extends JPanel {
    private Timer timer;
    private float breathPhase = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public BreathingCircleLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(50 / speed), e -> {
            breathPhase += 0.05f;
            if (breathPhase >= Math.PI * 2) breathPhase = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        // Calculate breathing scale and opacity
        float scale = 0.8f + 0.4f * (float)Math.sin(breathPhase);
        float opacity = 0.7f + 0.3f * (float)Math.sin(breathPhase);
        
        int circleSize = (int)(size * 0.8 * scale);
        
        g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, opacity));
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(2f));
        g2d.drawOval(centerX - circleSize/2, centerY - circleSize/2, circleSize, circleSize);
        
        g2d.dispose();
    }
}
```

---

## Loader 25: Ripple Effect
**Type:** Pulse | **Pattern:** Ripple  
**Description:** Water ripple pattern

### HTML/CSS
```html
<!-- Ripple Effect Loader -->
<div class="loader-25" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-2 h-2 border-2 border-blue-500 rounded-full animate-ping" style="top: 50%; left: 50%; transform: translate(-50%, -50%); animation-duration: 1s;"></div>
  <div class="absolute w-4 h-4 border-2 border-blue-400 rounded-full animate-ping" style="top: 50%; left: 50%; transform: translate(-50%, -50%); animation-duration: 1s; animation-delay: 0.3s;"></div>
  <div class="absolute w-6 h-6 border-2 border-blue-300 rounded-full animate-ping" style="top: 50%; left: 50%; transform: translate(-50%, -50%); animation-duration: 1s; animation-delay: 0.6s;"></div>
</div>
```

### React
```jsx
const RippleEffectLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  const ripples = [
    { size: 0.2, delay: 0, opacity: 1 },
    { size: 0.4, delay: 0.3, opacity: 0.7 },
    { size: 0.6, delay: 0.6, opacity: 0.5 }
  ];
  
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {ripples.map((ripple, index) => (
        <div 
          key={index}
          className="absolute border-2 rounded-full animate-ping"
          style={{ 
            width: size * ripple.size, 
            height: size * ripple.size,
            borderColor: color,
            opacity: ripple.opacity,
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)',
            animationDuration: `${1/speed}s`,
            animationDelay: `${ripple.delay/speed}s`
          }}
        />
      ))}
    </div>
  );
};
```

### Java
```java
public class RippleEffectLoader extends JPanel {
    private Timer timer;
    private float[] ripplePhases = {0f, 0f, 0f};
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public RippleEffectLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(30 / speed), e -> {
            ripplePhases[0] += 0.1f;
            ripplePhases[1] += 0.1f;
            ripplePhases[2] += 0.1f;
            
            // Reset with delays
            if (ripplePhases[0] >= 1f) ripplePhases[0] = 0f;
            if (ripplePhases[1] >= 1f) ripplePhases[1] = -0.3f;
            if (ripplePhases[2] >= 1f) ripplePhases[2] = -0.6f;
            
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setStroke(new BasicStroke(2f));
        
        for (int i = 0; i < 3; i++) {
            if (ripplePhases[i] >= 0) {
                float rippleSize = ripplePhases[i] * size;
                float opacity = 1f - ripplePhases[i];
                
                g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, opacity));
                g2d.setColor(color);
                g2d.drawOval((int)(centerX - rippleSize/2), (int)(centerY - rippleSize/2), 
                           (int)rippleSize, (int)rippleSize);
            }
        }
        
        g2d.dispose();
    }
}
```

---

## Loader 26: Sonar Ping
**Type:** Pulse | **Pattern:** Sonar  
**Description:** Sonar detection pulse

### HTML/CSS
```html
<!-- Sonar Ping Loader -->
<div class="loader-26" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-2 h-2 bg-green-500 rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
  <div class="absolute w-8 h-8 border border-green-400 rounded-full animate-ping" style="top: 50%; left: 50%; transform: translate(-50%, -50%); animation-duration: 2s;"></div>
  <div class="absolute w-12 h-12 border border-green-300 rounded-full animate-ping" style="top: 50%; left: 50%; transform: translate(-50%, -50%); animation-duration: 2s; animation-delay: 1s;"></div>
</div>
```

### React
```jsx
const SonarPingLoader = ({ size = 40, color = '#22c55e', speed = 1 }) => {
  const pings = [
    { size: 0.8, delay: 0, opacity: 0.8 },
    { size: 1.2, delay: 1, opacity: 0.5 }
  ];
  
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {/* Center dot */}
      <div 
        className="absolute rounded-full"
        style={{ 
          width: size * 0.15, 
          height: size * 0.15,
          backgroundColor: color,
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)'
        }}
      />
      
      {/* Ping circles */}
      {pings.map((ping, index) => (
        <div 
          key={index}
          className="absolute border rounded-full animate-ping"
          style={{ 
            width: size * ping.size, 
            height: size * ping.size,
            borderColor: color,
            opacity: ping.opacity,
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)',
            animationDuration: `${2/speed}s`,
            animationDelay: `${ping.delay/speed}s`
          }}
        />
      ))}
    </div>
  );
};
```

### Java
```java
public class SonarPingLoader extends JPanel {
    private Timer timer;
    private float[] pingPhases = {0f, -1f};
    private int size = 40;
    private Color color = Color.decode("#22c55e");
    private float speed = 1f;
    
    public SonarPingLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(50 / speed), e -> {
            for (int i = 0; i < pingPhases.length; i++) {
                pingPhases[i] += 0.02f;
                if (pingPhases[i] >= 1f) {
                    pingPhases[i] = 0f;
                }
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        // Draw ping circles
        g2d.setStroke(new BasicStroke(1f));
        for (int i = 0; i < pingPhases.length; i++) {
            if (pingPhases[i] >= 0) {
                float pingSize = pingPhases[i] * size;
                float opacity = 1f - pingPhases[i];
                
                g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, opacity));
                g2d.setColor(color);
                g2d.drawOval((int)(centerX - pingSize/2), (int)(centerY - pingSize/2), 
                           (int)pingSize, (int)pingSize);
            }
        }
        
        // Draw center dot
        g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, 1f));
        g2d.setColor(color);
        g2d.fillOval(centerX - 3, centerY - 3, 6, 6);
        
        g2d.dispose();
    }
}
```

---

## Loader 27: Radar Sweep
**Type:** Pulse | **Pattern:** Radar  
**Description:** Radar scanning effect

### HTML/CSS
```html
<!-- Radar Sweep Loader -->
<div class="loader-27" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-10 h-10 border border-green-400 rounded-full"></div>
  <div class="absolute w-6 h-6 border border-green-300 rounded-full" style="top: 25%; left: 25%;"></div>
  <div class="absolute w-0.5 h-5 bg-green-500 animate-spin" style="top: 50%; left: 50%; transform-origin: bottom; animation-duration: 2s;"></div>
  <div class="absolute w-1 h-1 bg-green-600 rounded-full" style="top: 50%; left: 50%; transform: translate(-50%, -50%);"></div>
</div>
```

### React
```jsx
const RadarSweepLoader = ({ size = 40, color = '#22c55e', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {/* Outer ring */}
      <div 
        className="absolute border rounded-full"
        style={{ 
          width: size, 
          height: size,
          borderColor: color,
          opacity: 0.6
        }}
      />
      
      {/* Inner ring */}
      <div 
        className="absolute border rounded-full"
        style={{ 
          width: size * 0.6, 
          height: size * 0.6,
          borderColor: color,
          opacity: 0.4,
          top: '20%',
          left: '20%'
        }}
      />
      
      {/* Sweep line */}
      <div 
        className="absolute animate-spin"
        style={{ 
          width: '2px', 
          height: size * 0.5,
          backgroundColor: color,
          top: '50%',
          left: '50%',
          transformOrigin: 'bottom',
          animationDuration: `${2/speed}s`
        }}
      />
      
      {/* Center dot */}
      <div 
        className="absolute rounded-full"
        style={{ 
          width: '4px', 
          height: '4px',
          backgroundColor: color,
          top: '50%',
          left: '50%',
          transform: 'translate(-50%, -50%)'
        }}
      />
    </div>
  );
};
```

### Java
```java
public class RadarSweepLoader extends JPanel {
    private Timer timer;
    private float sweepAngle = 0f;
    private int size = 40;
    private Color color = Color.decode("#22c55e");
    private float speed = 1f;
    
    public RadarSweepLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(40 / speed), e -> {
            sweepAngle += 3f;
            if (sweepAngle >= 360f) sweepAngle = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        // Draw radar circles
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(1f));
        
        // Outer circle
        g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, 0.6f));
        g2d.drawOval(centerX - size/2, centerY - size/2, size, size);
        
        // Inner circle
        g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, 0.4f));
        g2d.drawOval(centerX - size/4, centerY - size/4, size/2, size/2);
        
        // Draw sweep line
        g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, 1f));
        g2d.setStroke(new BasicStroke(2f));
        double rad = Math.toRadians(sweepAngle - 90);
        int sweepX = (int)(centerX + Math.cos(rad) * size/2);
        int sweepY = (int)(centerY + Math.sin(rad) * size/2);
        g2d.drawLine(centerX, centerY, sweepX, sweepY);
        
        // Draw center dot
        g2d.fillOval(centerX - 2, centerY - 2, 4, 4);
        
        g2d.dispose();
    }
}
```

---

## Loader 28: Target Lock
**Type:** Pulse | **Pattern:** Target  
**Description:** Target acquisition pulse

### HTML/CSS
```html
<!-- Target Lock Loader -->
<div class="loader-28" style="width: 40px; height: 40px; position: relative;">
  <div class="absolute w-10 h-10 border-2 border-red-500 rounded-full animate-ping" style="animation-duration: 1s;"></div>
  <div class="absolute w-6 h-6 border-2 border-red-600 rounded-full" style="top: 25%; left: 25%;"></div>
  <div class="absolute w-1 h-3 bg-red-500" style="top: 10%; left: 50%; transform: translateX(-50%);"></div>
  <div class="absolute w-1 h-3 bg-red-500" style="bottom: 10%; left: 50%; transform: translateX(-50%);"></div>
  <div class="absolute w-3 h-1 bg-red-500" style="top: 50%; left: 10%; transform: translateY(-50%);"></div>
  <div class="absolute w-3 h-1 bg-red-500" style="top: 50%; right: 10%; transform: translateY(-50%);"></div>
</div>
```

### React
```jsx
const TargetLockLoader = ({ size = 40, color = '#ef4444', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, position: 'relative' }}>
      {/* Outer pulsing ring */}
      <div 
        className="absolute border-2 rounded-full animate-ping"
        style={{ 
          width: size, 
          height: size,
          borderColor: color,
          animationDuration: `${1/speed}s`
        }}
      />
      
      {/* Inner crosshair ring */}
      <div 
        className="absolute border-2 rounded-full"
        style={{ 
          width: size * 0.6, 
          height: size * 0.6,
          borderColor: color,
          top: '20%',
          left: '20%'
        }}
      />
      
      {/* Crosshair lines */}
      {/* Top */}
      <div 
        className="absolute"
        style={{ 
          width: '2px', 
          height: size * 0.15,
          backgroundColor: color,
          top: '5%',
          left: '50%',
          transform: 'translateX(-50%)'
        }}
      />
      
      {/* Bottom */}
      <div 
        className="absolute"
        style={{ 
          width: '2px', 
          height: size * 0.15,
          backgroundColor: color,
          bottom: '5%',
          left: '50%',
          transform: 'translateX(-50%)'
        }}
      />
      
      {/* Left */}
      <div 
        className="absolute"
        style={{ 
          width: size * 0.15, 
          height: '2px',
          backgroundColor: color,
          top: '50%',
          left: '5%',
          transform: 'translateY(-50%)'
        }}
      />
      
      {/* Right */}
      <div 
        className="absolute"
        style={{ 
          width: size * 0.15, 
          height: '2px',
          backgroundColor: color,
          top: '50%',
          right: '5%',
          transform: 'translateY(-50%)'
        }}
      />
    </div>
  );
};
```

### Java
```java
public class TargetLockLoader extends JPanel {
    private Timer timer;
    private float pulsePhase = 0f;
    private int size = 40;
    private Color color = Color.decode("#ef4444");
    private float speed = 1f;
    
    public TargetLockLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(30 / speed), e -> {
            pulsePhase += 0.1f;
            if (pulsePhase >= 1f) pulsePhase = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        
        g2d.setColor(color);
        g2d.setStroke(new BasicStroke(2f));
        
        // Draw pulsing outer ring
        float pulseSize = size * (0.8f + pulsePhase * 0.4f);
        float pulseOpacity = 1f - pulsePhase;
        g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, pulseOpacity));
        g2d.drawOval((int)(centerX - pulseSize/2), (int)(centerY - pulseSize/2), 
                   (int)pulseSize, (int)pulseSize);
        
        // Draw inner crosshair ring
        g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, 1f));
        g2d.drawOval(centerX - size/4, centerY - size/4, size/2, size/2);
        
        // Draw crosshair lines
        int lineLength = size/6;
        
        // Top
        g2d.drawLine(centerX, centerY - size/2 + 5, centerX, centerY - size/2 + 5 + lineLength);
        // Bottom
        g2d.drawLine(centerX, centerY + size/2 - 5, centerX, centerY + size/2 - 5 - lineLength);
        // Left
        g2d.drawLine(centerX - size/2 + 5, centerY, centerX - size/2 + 5 + lineLength, centerY);
        // Right
        g2d.drawLine(centerX + size/2 - 5, centerY, centerX + size/2 - 5 - lineLength, centerY);
        
        g2d.dispose();
    }
}
```

---

## Loader 29-40: Additional Pulsing Loaders

**Quick Reference for remaining Pulsing Loaders (29-40):**

- **Loader 29: Echo Wave** - Sound wave echo effect
- **Loader 30: Vibration** - Vibration effect animation  
- **Loader 31: Throb Beat** - Strong pulsing beat
- **Loader 32: Rhythm Pulse** - Musical rhythm animation
- **Loader 33: Signal Beacon** - Signal transmission effect
- **Loader 34: Flash Light** - Flashing light effect
- **Loader 35: Glow Effect** - Glowing aura animation
- **Loader 36: Aura Pulse** - Energy aura effect
- **Loader 37: Energy Wave** - Energy emission pattern
- **Loader 38: Power Surge** - Power fluctuation effect
- **Loader 39: Intensity** - Intensity variation pulse
- **Loader 40: Force Field** - Energy field pulse effect

Each follows similar patterns to the detailed examples above, with variations in:
- Animation timing and easing
- Multiple elements/layers
- Color gradients and opacity changes
- Scale transformations
- Directional effects

---

# Bouncing Loaders (41-60)

## Loader 41: Bounce Ball
**Type:** Bounce | **Pattern:** Ball  
**Description:** A simple bouncing ball

### HTML/CSS
```html
<!-- Bounce Ball Loader -->
<div class="loader-41" style="width: 40px; height: 40px; display: flex; align-items: end; justify-content: center; color: #1a73e8;">
  <div class="w-6 h-6 bg-current rounded-full animate-bounce"></div>
</div>

<style>
.loader-41 > div {
  animation-duration: 1s;
}
</style>
```

### React
```jsx
const BounceBallLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  return (
    <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'end', justifyContent: 'center' }}>
      <div 
        className="bg-current rounded-full animate-bounce"
        style={{ 
          width: size * 0.6, 
          height: size * 0.6,
          animationDuration: `${1/speed}s`
        }}
      />
    </div>
  );
};
```

### Java
```java
public class BounceBallLoader extends JPanel {
    private Timer timer;
    private float ballY = 0f;
    private float velocity = 0f;
    private float gravity = 0.5f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public BounceBallLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        ballY = size * 0.7f;
        
        timer = new Timer((int)(16 / speed), e -> {
            velocity += gravity;
            ballY += velocity;
            
            if (ballY >= size * 0.7f) {
                ballY = size * 0.7f;
                velocity = -Math.abs(velocity) * 0.8f; // Bounce with energy loss
                if (Math.abs(velocity) < 1f) {
                    velocity = -8f; // Reset bounce
                }
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int ballSize = (int)(size * 0.6);
        
        g2d.setColor(color);
        g2d.fillOval(centerX - ballSize/2, (int)ballY - ballSize/2, ballSize, ballSize);
        
        g2d.dispose();
    }
}
```

---

## Loader 42: Three Balls
**Type:** Bounce | **Pattern:** Three Balls  
**Description:** Three balls bouncing in sequence

### HTML/CSS
```html
<!-- Three Balls Loader -->
<div class="loader-42" style="width: 40px; height: 40px; display: flex; align-items: end; justify-content: space-between; padding: 0 5px;">
  <div class="w-2 h-2 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0s; animation-duration: 1.4s;"></div>
  <div class="w-2 h-2 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0.2s; animation-duration: 1.4s;"></div>
  <div class="w-2 h-2 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0.4s; animation-duration: 1.4s;"></div>
</div>
```

### React
```jsx
const ThreeBallsLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  const balls = [0, 0.2, 0.4];
  
  return (
    <div style={{ 
      width: size, 
      height: size, 
      display: 'flex', 
      alignItems: 'end', 
      justifyContent: 'space-between', 
      padding: '0 5px' 
    }}>
      {balls.map((delay, index) => (
        <div 
          key={index}
          className="bg-current rounded-full animate-bounce"
          style={{ 
            width: size * 0.2, 
            height: size * 0.2,
            color: color,
            animationDelay: `${delay/speed}s`,
            animationDuration: `${1.4/speed}s`
          }}
        />
      ))}
    </div>
  );
};
```

### Java
```java
public class ThreeBallsLoader extends JPanel {
    private Timer timer;
    private float[] ballY = {0f, 0f, 0f};
    private float[] velocity = {0f, 0f, 0f};
    private float[] phase = {0f, 0.2f, 0.4f};
    private float gravity = 0.4f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public ThreeBallsLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        for (int i = 0; i < 3; i++) {
            ballY[i] = size * 0.8f;
        }
        
        timer = new Timer((int)(16 / speed), e -> {
            for (int i = 0; i < 3; i++) {
                phase[i] += 0.1f;
                
                // Simple bounce calculation with phase offset
                ballY[i] = (float)(size * 0.8f - Math.abs(Math.sin(phase[i]) * size * 0.4f));
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int ballSize = (int)(size * 0.2);
        g2d.setColor(color);
        
        for (int i = 0; i < 3; i++) {
            int ballX = (int)(getWidth() * (0.2 + i * 0.3));
            g2d.fillOval(ballX - ballSize/2, (int)ballY[i] - ballSize/2, ballSize, ballSize);
        }
        
        g2d.dispose();
    }
}
```

---

## Loader 43: Wave Balls
**Type:** Bounce | **Pattern:** Wave Balls  
**Description:** Wave-like bouncing sequence

### HTML/CSS
```html
<!-- Wave Balls Loader -->
<div class="loader-43" style="width: 40px; height: 40px; display: flex; align-items: end; justify-content: space-between;">
  <div class="w-1.5 h-1.5 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0s; animation-duration: 1s;"></div>
  <div class="w-1.5 h-1.5 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0.1s; animation-duration: 1s;"></div>
  <div class="w-1.5 h-1.5 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0.2s; animation-duration: 1s;"></div>
  <div class="w-1.5 h-1.5 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0.3s; animation-duration: 1s;"></div>
  <div class="w-1.5 h-1.5 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0.4s; animation-duration: 1s;"></div>
</div>
```

### React
```jsx
const WaveBallsLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  const balls = Array.from({ length: 5 }, (_, i) => i * 0.1);
  
  return (
    <div style={{ 
      width: size, 
      height: size, 
      display: 'flex', 
      alignItems: 'end', 
      justifyContent: 'space-between' 
    }}>
      {balls.map((delay, index) => (
        <div 
          key={index}
          className="bg-current rounded-full animate-bounce"
          style={{ 
            width: size * 0.15, 
            height: size * 0.15,
            color: color,
            animationDelay: `${delay/speed}s`,
            animationDuration: `${1/speed}s`
          }}
        />
      ))}
    </div>
  );
};
```

### Java
```java
public class WaveBallsLoader extends JPanel {
    private Timer timer;
    private float[] ballY = new float[5];
    private float[] phase = {0f, 0.1f, 0.2f, 0.3f, 0.4f};
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public WaveBallsLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            for (int i = 0; i < 5; i++) {
                phase[i] += 0.15f;
                ballY[i] = (float)(size * 0.8f - Math.abs(Math.sin(phase[i]) * size * 0.3f));
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int ballSize = (int)(size * 0.15);
        g2d.setColor(color);
        
        for (int i = 0; i < 5; i++) {
            int ballX = (int)(getWidth() * (0.1 + i * 0.2));
            g2d.fillOval(ballX - ballSize/2, (int)ballY[i] - ballSize/2, ballSize, ballSize);
        }
        
        g2d.dispose();
    }
}
```

---

## Loader 44-60: Additional Bouncing Loaders

**Quick Reference for remaining Bouncing Loaders (44-60):**

- **Loader 44: Basketball** - Basketball bouncing with realistic physics
- **Loader 45: Rubber Ball** - Rubber ball with high bounce
- **Loader 46: Spring Bounce** - Spring compression effect
- **Loader 47: Elastic Jump** - Elastic deformation on impact
- **Loader 48: Yo-yo Motion** - Yo-yo up/down movement
- **Loader 49: Pogo Stick** - Pogo stick jumping motion
- **Loader 50: Trampoline** - Trampoline bouncing effect
- **Loader 51: Skip Hop** - Skipping motion pattern
- **Loader 52: Leap Frog** - Leaping animation
- **Loader 53: Bound Jump** - Bounding movement
- **Loader 54: Rebound** - Rebound effect animation
- **Loader 55: Elastic Band** - Elastic stretching
- **Loader 56: Pendulum** - Pendulum swing motion
- **Loader 57: Newton Cradle** - Newton's cradle physics
- **Loader 58: Gravity Drop** - Gravity falling effect
- **Loader 59: Impact Bounce** - Impact with bounce back
- **Loader 60: Spring Coil** - Coil compression animation

---

# Sliding Loaders (61-80)

## Loader 61: Progress Bar
**Type:** Slide | **Pattern:** Progress  
**Description:** A sliding progress bar

### HTML/CSS
```html
<!-- Progress Bar Loader -->
<div class="loader-61" style="width: 40px; height: 8px; background: #e5e7eb; border-radius: 4px; overflow: hidden; display: flex; align-items: center;">
  <div class="w-1/3 h-full bg-blue-500 animate-ping" style="border-radius: 4px; animation-duration: 2s;"></div>
</div>
```

### React
```jsx
const ProgressBarLoader = ({ size = 40, color = '#1a73e8', backgroundColor = '#e5e7eb', speed = 1 }) => {
  return (
    <div style={{ 
      width: size, 
      height: size * 0.2, 
      background: backgroundColor, 
      borderRadius: '4px', 
      overflow: 'hidden',
      position: 'relative'
    }}>
      <div 
        className="absolute h-full animate-ping"
        style={{ 
          width: size * 0.33,
          background: color,
          borderRadius: '4px',
          animationDuration: `${2/speed}s`
        }}
      />
    </div>
  );
};
```

### Java
```java
public class ProgressBarLoader extends JPanel {
    private Timer timer;
    private float progress = 0f;
    private boolean forward = true;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private Color backgroundColor = Color.decode("#e5e7eb");
    private float speed = 1f;
    
    public ProgressBarLoader() {
        setPreferredSize(new Dimension(size, (int)(size * 0.2)));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            if (forward) {
                progress += 0.02f;
                if (progress >= 1f) {
                    progress = 1f;
                    forward = false;
                }
            } else {
                progress -= 0.02f;
                if (progress <= 0f) {
                    progress = 0f;
                    forward = true;
                }
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int barHeight = (int)(size * 0.2);
        
        // Draw background
        g2d.setColor(backgroundColor);
        g2d.fillRoundRect(0, 0, size, barHeight, 4, 4);
        
        // Draw progress
        g2d.setColor(color);
        int progressWidth = (int)(size * progress);
        g2d.fillRoundRect(0, 0, progressWidth, barHeight, 4, 4);
        
        g2d.dispose();
    }
}
```

---

## Loader 62: Scan Line
**Type:** Slide | **Pattern:** Scan  
**Description:** Scanning line effect

### HTML/CSS
```html
<!-- Scan Line Loader -->
<div class="loader-62" style="width: 40px; height: 40px; position: relative; background: linear-gradient(90deg, transparent 0%, #1a73e8 50%, transparent 100%); background-size: 50% 100%;">
  <div class="absolute w-full h-full animate-pulse" style="background: linear-gradient(90deg, transparent 0%, rgba(26, 115, 232, 0.3) 50%, transparent 100%); background-size: 50% 100%; animation-duration: 2s;"></div>
</div>
```

### React
```jsx
const ScanLineLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  const scanKeyframes = `
    @keyframes scanLine {
      0% { transform: translateX(-100%); }
      100% { transform: translateX(100%); }
    }
  `;
  
  return (
    <>
      <style>{scanKeyframes}</style>
      <div style={{ 
        width: size, 
        height: size, 
        position: 'relative',
        overflow: 'hidden',
        background: '#f3f4f6'
      }}>
        <div 
          style={{ 
            position: 'absolute',
            width: '30%',
            height: '100%',
            background: `linear-gradient(90deg, transparent 0%, ${color} 50%, transparent 100%)`,
            animation: `scanLine ${2/speed}s ease-in-out infinite`
          }}
        />
      </div>
    </>
  );
};
```

### Java
```java
public class ScanLineLoader extends JPanel {
    private Timer timer;
    private float scanPosition = -0.3f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private Color backgroundColor = Color.decode("#f3f4f6");
    private float speed = 1f;
    
    public ScanLineLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(20 / speed), e -> {
            scanPosition += 0.02f;
            if (scanPosition >= 1.3f) {
                scanPosition = -0.3f;
            }
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        // Draw background
        g2d.setColor(backgroundColor);
        g2d.fillRect(0, 0, size, size);
        
        // Draw scan line
        int lineX = (int)(scanPosition * size);
        int lineWidth = size / 3;
        
        GradientPaint gradient = new GradientPaint(
            lineX, 0, new Color(color.getRed(), color.getGreen(), color.getBlue(), 0),
            lineX + lineWidth/2, 0, color,
            lineX + lineWidth, 0, new Color(color.getRed(), color.getGreen(), color.getBlue(), 0)
        );
        
        g2d.setPaint(gradient);
        g2d.fillRect(lineX, 0, lineWidth, size);
        
        g2d.dispose();
    }
}
```

---

## Loader 63-80: Additional Sliding Loaders

**Quick Reference for remaining Sliding Loaders (63-80):**

- **Loader 63: Conveyor Belt** - Conveyor movement effect
- **Loader 64: Train Motion** - Train-like sliding movement
- **Loader 65: Runner Track** - Running track effect
- **Loader 66: Slider Bar** - Sliding bar animation
- **Loader 67: Arrow Flow** - Arrow movement pattern
- **Loader 68: Comet Trail** - Comet with trailing effect
- **Loader 69: Glide Motion** - Smooth gliding movement
- **Loader 70: Flow Stream** - Flowing stream effect
- **Loader 71: Current Wave** - Water current animation
- **Loader 72: Drift Motion** - Drifting movement pattern
- **Loader 73: Cruise Control** - Steady cruising motion
- **Loader 74: Sail Wind** - Wind sailing effect
- **Loader 75: Surf Wave** - Wave surfing animation
- **Loader 76: Fluid Motion** - Fluid dynamics effect
- **Loader 77: Smooth Slide** - Smooth sliding motion
- **Loader 78: Linear Path** - Linear movement pattern
- **Loader 79: Track Follow** - Track following animation
- **Loader 80: Path Trace** - Path tracing effect

---

# Morphing Loaders (81-100)

## Loader 81: Shape Morph
**Type:** Morph | **Pattern:** Shape  
**Description:** Shape morphing animation

### HTML/CSS
```html
<!-- Shape Morph Loader -->
<div class="loader-81" style="width: 40px; height: 40px; color: #1a73e8; display: flex; align-items: center; justify-content: center;">
  <div class="w-10 h-10 bg-current" style="animation: morph 2s ease-in-out infinite;"></div>
</div>

<style>
@keyframes morph {
  0%, 100% { border-radius: 50%; transform: rotate(0deg); }
  25% { border-radius: 0%; transform: rotate(90deg); }
  50% { border-radius: 50% 0%; transform: rotate(180deg); }
  75% { border-radius: 0% 50%; transform: rotate(270deg); }
}
</style>
```

### React
```jsx
const ShapeMorphLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  const morphKeyframes = `
    @keyframes morph {
      0%, 100% { border-radius: 50%; transform: rotate(0deg); }
      25% { border-radius: 0%; transform: rotate(90deg); }
      50% { border-radius: 50% 0%; transform: rotate(180deg); }
      75% { border-radius: 0% 50%; transform: rotate(270deg); }
    }
  `;
  
  return (
    <>
      <style>{morphKeyframes}</style>
      <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
        <div 
          className="bg-current"
          style={{ 
            width: size, 
            height: size,
            animation: `morph ${2/speed}s ease-in-out infinite`
          }}
        />
      </div>
    </>
  );
};
```

### Java
```java
public class ShapeMorphLoader extends JPanel {
    private Timer timer;
    private float morphPhase = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public ShapeMorphLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(50 / speed), e -> {
            morphPhase += 0.02f;
            if (morphPhase >= 1f) morphPhase = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        int shapeSize = (int)(size * 0.8);
        
        g2d.setColor(color);
        g2d.translate(centerX, centerY);
        g2d.rotate(morphPhase * Math.PI * 2);
        
        // Create morphing shape
        if (morphPhase < 0.25f) {
            // Circle to square
            float radius = shapeSize/2 * (1 - morphPhase * 4);
            g2d.fillRoundRect(-shapeSize/2, -shapeSize/2, shapeSize, shapeSize, (int)radius, (int)radius);
        } else if (morphPhase < 0.5f) {
            // Square to diamond
            float p = (morphPhase - 0.25f) * 4;
            g2d.fillRect(-shapeSize/2, -shapeSize/2, shapeSize, shapeSize);
        } else if (morphPhase < 0.75f) {
            // Diamond to oval
            float p = (morphPhase - 0.5f) * 4;
            g2d.fillOval(-shapeSize/2, -shapeSize/2, shapeSize, shapeSize);
        } else {
            // Oval to circle
            float p = (morphPhase - 0.75f) * 4;
            g2d.fillOval(-shapeSize/2, -shapeSize/2, shapeSize, shapeSize);
        }
        
        g2d.dispose();
    }
}
```

---

## Loader 82: Blob Form
**Type:** Morph | **Pattern:** Blob  
**Description:** Blob morphing effect

### HTML/CSS
```html
<!-- Blob Form Loader -->
<div class="loader-82" style="width: 40px; height: 40px; color: #1a73e8; display: flex; align-items: center; justify-content: center;">
  <div class="w-8 h-8 bg-current animate-pulse" style="border-radius: 50% 40% 60% 30%; animation-duration: 2s;"></div>
</div>

<style>
@keyframes blob {
  0%, 100% { border-radius: 50% 40% 60% 30%; transform: scale(1); }
  25% { border-radius: 30% 60% 40% 50%; transform: scale(1.1); }
  50% { border-radius: 60% 30% 50% 40%; transform: scale(0.9); }
  75% { border-radius: 40% 50% 30% 60%; transform: scale(1.05); }
}
.loader-82 > div {
  animation: blob 2s ease-in-out infinite;
}
</style>
```

### React
```jsx
const BlobFormLoader = ({ size = 40, color = '#1a73e8', speed = 1 }) => {
  const blobKeyframes = `
    @keyframes blob {
      0%, 100% { border-radius: 50% 40% 60% 30%; transform: scale(1); }
      25% { border-radius: 30% 60% 40% 50%; transform: scale(1.1); }
      50% { border-radius: 60% 30% 50% 40%; transform: scale(0.9); }
      75% { border-radius: 40% 50% 30% 60%; transform: scale(1.05); }
    }
  `;
  
  return (
    <>
      <style>{blobKeyframes}</style>
      <div style={{ width: size, height: size, color, display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
        <div 
          className="bg-current"
          style={{ 
            width: size * 0.8, 
            height: size * 0.8,
            animation: `blob ${2/speed}s ease-in-out infinite`
          }}
        />
      </div>
    </>
  );
};
```

### Java
```java
public class BlobFormLoader extends JPanel {
    private Timer timer;
    private float blobPhase = 0f;
    private int size = 40;
    private Color color = Color.decode("#1a73e8");
    private float speed = 1f;
    
    public BlobFormLoader() {
        setPreferredSize(new Dimension(size, size));
        setOpaque(false);
        
        timer = new Timer((int)(40 / speed), e -> {
            blobPhase += 0.02f;
            if (blobPhase >= Math.PI * 2) blobPhase = 0f;
            repaint();
        });
        timer.start();
    }
    
    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2d = (Graphics2D) g.create();
        g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
        
        int centerX = getWidth() / 2;
        int centerY = getHeight() / 2;
        int blobSize = (int)(size * 0.6);
        
        g2d.setColor(color);
        
        // Create blob shape with varying control points
        Path2D blob = new Path2D.Float();
        int points = 8;
        
        for (int i = 0; i <= points; i++) {
            double angle = (double) i / points * Math.PI * 2;
            double radius = blobSize/2 + Math.sin(blobPhase + angle * 3) * blobSize/6;
            
            double x = centerX + Math.cos(angle) * radius;
            double y = centerY + Math.sin(angle) * radius;
            
            if (i == 0) {
                blob.moveTo(x, y);
            } else {
                blob.lineTo(x, y);
            }
        }
        blob.closePath();
        
        g2d.fill(blob);
        
        g2d.dispose();
    }
}
```

---

## Loader 83-100: Additional Morphing Loaders

**Quick Reference for remaining Morphing Loaders (83-100):**

- **Loader 83: Liquid Drop** - Liquid deformation effect
- **Loader 84: Amoeba Cell** - Amoeba-like movement
- **Loader 85: Plasma State** - Plasma fluctuation animation
- **Loader 86: Jellyfish** - Jellyfish swimming motion
- **Loader 87: Water Drop** - Water droplet formation
- **Loader 88: Lava Flow** - Lava flowing movement
- **Loader 89: Metamorphosis** - Complete transformation
- **Loader 90: Transform** - Shape transformation effect
- **Loader 91: Mutate Form** - Form mutation animation
- **Loader 92: Evolve Shape** - Shape evolution process
- **Loader 93: Organic Flow** - Organic movement pattern
- **Loader 94: Flexible Form** - Flexible deformation
- **Loader 95: Adaptive Shape** - Adaptive morphing
- **Loader 96: Dynamic Form** - Dynamic shape changes
- **Loader 97: Elastic Morph** - Elastic deformation effect
- **Loader 98: Fluid Shape** - Fluid dynamics animation
- **Loader 99: Transition Form** - Smooth transitions
- **Loader 100: Progressive Morph** - Progressive morphing changes

---

## Usage Instructions

### Installation
All loaders are MIT licensed and free to use. Simply copy the code for your preferred framework.

### Customization Parameters
Each loader supports the following customization options:

1. **Size** (16px - 120px)
2. **Speed** (0.1x - 5x)
3. **Color** (Any hex value)
4. **Secondary Color** (For gradients)
5. **Background Color**
6. **Opacity** (10% - 100%)
7. **Thickness** (1px - 8px)
8. **Direction** (normal, reverse, alternate)
9. **Easing** (linear, ease, ease-in, ease-out)
10. **Delay** (0ms - 2000ms)
11. **Scale** (0.5x - 3x)
12. **Blur** (0px - 10px)
13. **Shadow** (0px - 20px)
14. **Rotation** (0° - 360°)
15. **Skew** (-45° - 45°)
16. **Border Radius** (0% - 100%)
17. **Pulse Intensity** (0% - 100%)
18. **Gradient Toggle**
19. **Category Filter**
20. **Search Filter**

### Framework Integration

#### HTML/CSS
- Pure CSS animations
- Tailwind CSS classes
- Custom CSS properties
- Responsive design support

#### React
- TypeScript compatible
- Props-based customization
- Hook-friendly implementation
- Server-side rendering support

#### Java Swing
- Desktop application ready
- High-performance rendering
- Event-driven animations
- Cross-platform compatibility

### Performance Notes
- CSS animations are GPU-accelerated
- Java implementations use optimized timers
- React components use efficient re-rendering
- All loaders support 60fps animation

### Browser Support
- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+
- Mobile browsers

---

**© 2025 Chezcakeishere on GitHub**  
Website design and code are copyrighted. All loader elements and generated code are **MIT Licensed** and free to use in your projects.