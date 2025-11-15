# 🎬 JSX Rendering

A stunning animated video project built with [Remotion](https://www.remotion.dev/) featuring liquid metal effects, prismatic animations, and colorful bending gradients.

## 🎨 Features

- **Liquid Metal Effect** - Smooth, flowing liquid metal shader animations using `@paper-design/shaders-react`
- **3D Prismatic Effects** - WebGL-powered prism shader with interactive hover effects
- **Colorful Gradient Animations** - Dynamic color bending and warping effects using Three.js
- **Customizable Logo Animation** - Animated arcs, atoms, and rotating elements
- **High-Quality Output** - Configured for VP9 codec with transparent PNG support

## 📦 Dependencies

- **remotion** - Video rendering framework
- **three** - 3D graphics library for color effects
- **ogl** - Lightweight WebGL library for prism effects
- **react** - UI framework
- **@paper-design/shaders-react** - Advanced shader effects

## 🚀 Getting Started

### Install Dependencies

```bash
npm install
```

### Start Development

```bash
npm run dev
```

This opens Remotion Studio where you can preview your video in real-time.

### Build for Production

```bash
npm run build
```

### Render Video

```bash
npx remotion render LiquidMetalVideo out/video.mp4
```

## 📁 Project Structure

```
src/
├── Root.jsx                 # Main composition setup
├── LiquidMetal.jsx          # Liquid metal effect component
├── Prism.jsx                # Prismatic shader effect (WebGL)
├── ColorBends.jsx           # Color bending animation (Three.js)
├── index.ts                 # Entry point
│
└── HelloWorld/              # Logo animation components
    ├── Logo.tsx             # Main logo component
    ├── Arc.tsx              # Animated arc element
    ├── Atom.tsx             # Central atom circle
    ├── Title.tsx            # Animated title text
    ├── Subtitle.tsx         # Subtitle component
    └── constants.ts         # Color and font constants
```

## 🎬 Compositions

### LiquidMetalVideo

The main composition configured in [`Root.jsx`](src/Root.jsx):

- **Duration**: 600 frames at 50 fps (12 seconds)
- **Resolution**: 1093×304 pixels
- **Component**: [`LiquidMetal`](src/LiquidMetal.jsx)

## 🎨 Key Components

### [`LiquidMetal.jsx`](src/LiquidMetal.jsx)
Displays a liquid metal effect with the following properties:
- Smooth distortion and contour effects
- Configurable color tint and softness
- Diamond shape with customizable angle and rotation

### [`Prism.jsx`](src/Prism.jsx)
WebGL-based prismatic effect with:
- Multiple animation types: `rotate`, `hover`, `3drotate`
- Customizable glow, bloom, and noise
- Interactive hover response
- Performance-optimized with requestAnimationFrame

### [`ColorBends.jsx`](src/ColorBends.jsx)
Three.js shader-based color bending with:
- Multi-color support (up to 8 colors)
- Dynamic warp strength and frequency
- Mouse influence and parallax effects
- Transparent background support

### [`HelloWorld/Logo.tsx`](src/HelloWorld/Logo.tsx)
Animated logo with:
- Rotating arcs with gradient colors
- Central atom circle
- Spring-based animations
- 360-degree rotation over duration

## ⚙️ Configuration

### Video Settings ([`remotion.config.ts`](remotion.config.ts))

```typescript
Config.setVideoImageFormat("png");    // PNG for best quality
Config.setCodec("vp9");              // VP9 supports transparency
Config.setOverwriteOutput(true);     // Overwrite existing files
```

### Customization

Edit these files to customize your video:

- **Colors**: [`src/HelloWorld/constants.ts`](src/HelloWorld/constants.ts)
- **Font & Typography**: [`src/HelloWorld/Title.tsx`](src/HelloWorld/Title.tsx)
- **Animation Duration**: [`src/Root.jsx`](src/Root.jsx)
- **Liquid Metal Settings**: [`src/LiquidMetal.jsx`](src/LiquidMetal.jsx)

## 📊 Animation Properties

### Prism Component
```jsx
<Prism
  height={3.5}              // Pyramid height
  baseWidth={5.5}           // Base width
  animationType="rotate"    // 'rotate' | 'hover' | '3drotate'
  glow={1}                  // Glow intensity
  scale={3.6}               // Render scale
  transparent={true}        // Transparent background
  hoverStrength={2}         // Hover response strength
  timeScale={0.5}           // Animation speed
/>
```

### ColorBends Component
```jsx
<ColorBends
  colors={['#FF0000', '#00FF00', '#0000FF']}
  transparent={true}
  scale={1}
  frequency={1}
  warpStrength={1}
  mouseInfluence={1}
  parallax={0.5}
  noise={0.1}
/>
```

## 🛠️ Available Scripts

```bash
npm run dev      # Start Remotion Studio
npm run build    # Bundle project
npm run lint     # Run ESLint and TypeScript checks
npm run upgrade  # Upgrade Remotion to latest version
```

## 📝 TypeScript Support

This project uses TypeScript with strict mode enabled. All type definitions are included:

- [`tsconfig.json`](tsconfig.json) - TypeScript configuration
- Zod schemas for runtime validation in compositions

## 🐛 Troubleshooting

**Video not rendering?**
- Ensure FFmpeg is installed
- Check video codec compatibility
- Verify frame count and fps settings

**Shader effects not displaying?**
- Update graphics drivers
- Check WebGL support in your browser
- Verify hardware acceleration is enabled

**Performance issues?**
- Reduce resolution in development
- Lower `dpr` (devicePixelRatio) in Prism/Shaders
- Use `suspendWhenOffscreen` for off-screen effects

## 📚 Learn More

- [Remotion Documentation](https://www.remotion.dev/docs)
- [Three.js Documentation](https://threejs.org/docs)
- [WebGL Best Practices](https://www.khronos.org/webgl/wiki/Best_Practices)

## 🤝 Support

- [Remotion Discord Community](https://discord.gg/6VzzNDwUwV)
- [GitHub Issues](https://github.com/remotion-dev/remotion/issues)

## 📄 License

Refer to the [Remotion License](https://github.com/remotion-dev/remotion/blob/main/LICENSE.md) for licensing requirements.

---

**Created with ❤️ using Remotion**
