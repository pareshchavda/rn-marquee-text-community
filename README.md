# React Native Marquee Text 🚀

![Horizontal and Vertical Marquee Demo](rn-marquee-text.gif)

[![Try it on Expo Snack](https://img.shields.io/badge/Try%20it-Expo%20Snack-4630EB?style=for-the-badge&logo=expo)](https://snack.expo.dev/@pareshchavda/rn-marquee-text)

## Features ✨

- **Multi-directional scrolling**: Horizontal and vertical marquee effects
- **Animation modes**: Loop and bounce animations
- **Performance optimized**: Built with React Native Reanimated 3
- **Customizable**: Control speed, delay, spacing, and more
- **Flexible content**: Supports both text and custom components
- **TypeScript ready**: Complete type definitions included

## Installation 📦

```bash
# Using npm
npm install rn-marquee-text react-native-reanimated

# Using yarn
yarn add rn-marquee-text react-native-reanimated
```

### Peer Dependencies
Ensure you've properly installed and configured:
- [React Native Reanimated](https://docs.swmansion.com/react-native-reanimated/docs/fundamentals/installation)

## Usage 🚀

### Basic Implementation
```jsx
import React from 'react';
import { StyleSheet, View } from 'react-native';
import { Marquee } from 'rn-marquee-text';

const App = () => (
  <View style={styles.container}>
    <Marquee
      style={styles.marquee}
      speed={40}
      textStyle={styles.text}
    >
      Your scrolling text goes here
    </Marquee>
  </View>
);

const styles = StyleSheet.create({
  container: { flex: 1, justifyContent: 'center', padding: 20 },
  marquee: { height: 50, backgroundColor: '#f5f5f5', borderRadius: 8 },
  text: { fontSize: 16, color: '#333' }
});

export default App;
```

## API Reference 📚

### Props
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `children` | React.ReactNode | Required | Content to scroll (string or components) |
| `mode` | 'loop' \| 'bounce' | 'loop' | Animation behavior |
| `speed` | number | 30 | Pixels per second |
| `direction` | 'horizontal' \| 'vertical' | 'horizontal' | Scroll direction |
| `enabled` | boolean | true | Animation active state |
| `delay` | number | 1500 | Initial delay (ms) before starting |
| `endPauseDuration` | number | 1000 | Pause at end (bounce mode only) |
| `gap` | number | 20 | Gap between repeating text loops |
| `spacing` | number | 20 | **Deprecated**: Use `gap` instead |
| `reverse` | boolean | false | Reverse the animation direction |
| `backgroundColor` | string | 'transparent' | Background color for the container |
| `frameRate` | number | - | Custom frame rate for animation |
| `onAnimationStart` | function | - | Callback when animation starts |
| `onAnimationStop` | function | - | Callback when animation stops |
| `style` | ViewStyle | - | Container style |
| `textStyle` | TextStyle | - | Text style (when children is a string) |

### Methods (via ref)
```jsx
const marqueeRef = useRef();

// Start animation
marqueeRef.current?.start();

// Stop animation
marqueeRef.current?.stop();

// Check if active
const isActive = marqueeRef.current?.isActive;
```

## Examples 🎨

### Comprehensive Demo Example
```jsx
import React from 'react';
import { SafeAreaView, View, Text, StyleSheet } from 'react-native';
import { AutoScroll, Marquee } from 'rn-marquee-text';

export default function App() {
  return (
    <SafeAreaView style={{ flex: 1, padding: 16, gap: 24 }}>
      <Text style={{ fontSize: 20, fontWeight: 'bold' }}>Marquee Text Demo</Text>

      <View style={{ borderRadius: 8, overflow: 'hidden' }}>
        <Marquee speed={80}>
          This is a long scrolling text that demonstrates the marquee functionality
        </Marquee>
      </View>

      <View style={{ borderRadius: 8, overflow: 'hidden' }}>
        <Marquee
          speed={120}
          backgroundColor="#1a365d"
          textStyle={{ color: '#f0f4f8', fontSize: 14 }}
        >
          Faster scrolling example with different colors
        </Marquee>
      </View>

      <View style={{ width: '100%', borderRadius: 8, overflow: 'hidden' }}>
        <Marquee
          speed={100}
          backgroundColor="#7b341e"
          textStyle={{ color: '#fffaf0', fontSize: 18 }}
        >
          Breaking News: This is a full-width marquee text component that scrolls horizontally
        </Marquee>
      </View>

      <View style={{ marginVertical: 10, borderRadius: 8, overflow: 'hidden' }}>
        <Marquee
          speed={50}
          backgroundColor="#fff"
          textStyle={{ color: '#0000ff', fontSize: 16 }}
        >
          This text will scroll horizontally continuously
        </Marquee>
      </View>

      <AutoScroll mode='loop' gap={50} style={styles.cardScroller} direction="horizontal">
        <View style={styles.contentContainer}>
          {[1, 2, 3, 4, 5].map((item) => (
            <View key={item} style={styles.card}>
              <Text style={styles.cardText}>Card {item}</Text>
            </View>
          ))}
        </View>
      </AutoScroll>
      
      <AutoScroll mode='loop' gap={50} style={styles.cardScroller} direction="horizontal">
        <Text style={styles.cardText}>Legacy AutoScroll component with seamless loop 🎉</Text>
      </AutoScroll>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  cardScroller: {
    height: 120,
    width: '100%',
    marginTop: 10,
  },
  contentContainer: {
    flexDirection: 'row',
    padding: 10,
  },
  card: {
    width: 100,
    height: 100,
    backgroundColor: '#f0f0f0',
    borderRadius: 8,
    marginRight: 10,
    justifyContent: 'center',
    alignItems: 'center',
  },
  cardText: {
    fontSize: 16,
    fontWeight: 'bold',
  },
});
```

## Troubleshooting 🛠️

**Animation not working?**
- Verify Reanimated installation
- Check babel.config.js for Reanimated plugin

**Text not visible?**
- Ensure container has proper dimensions
- Verify text color contrasts with background

**Performance issues?**
- Reduce animation speed
- Simplify marquee content
- Use `frameRate` prop to limit FPS

## Contributing 🤝
Contributions are welcome! Please:
1. Open an issue to discuss changes
2. Ensure tests are updated
3. Maintain consistent code style

## License 📄
MIT © PareshChavda(https://github.com/pareshchavda)



