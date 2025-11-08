##  BCI Smartphone - Mobile App Release

### What We're Trying to Achieve
This mobile app is part of a brain-computer interface (BCI) system that enables hands-free smartphone control. Our goal is to make smartphones more accessible by combining BCI signals (from Emotiv headsets) with intelligent gaze tracking and gesture automation.

### What This App Does
- **Background Service**: Runs continuously in the background (like Messenger) to listen for BCI commands from the server
- **Gaze Tracking**: Uses the front camera and device sensors to predict where you're looking on the screen using a trained AI model
- **Gesture Automation**: Performs gestures (swipe up/down, double tap, etc.) based on BCI commands received from the server
- **Real-time HUD**: Displays sensor data and gaze predictions in real-time for monitoring and debugging

###  Gaze Calibration - Why It Matters & How to Use It

#### Why Calibration Helps

**The Problem**: Gaze tracking accuracy varies significantly between users because:
- **Face Structure**: Everyone has unique facial features, eye shapes, and eye spacing
- **Device Positioning**: How you hold your phone (distance, angle, orientation) affects measurements
- **Environmental Factors**: Lighting conditions, glasses, and viewing angles all impact accuracy
- **Personal Patterns**: Your natural head movements and eye behavior are unique

**The Solution**: Calibration creates a personalized mapping between your eye movements and screen coordinates. The app can work without calibration (using a general AI model), but calibration dramatically improves accuracy by learning your specific characteristics.

**What Calibration Does**:
1. **Collects Reference Points**: Records your eye position, head pose, and device sensors while you look at known screen locations
2. **Creates Personal Profile**: Builds a mathematical model of how YOUR eyes relate to YOUR screen
3. **Enhances Predictions**: Uses this profile to refine the AI model's predictions in real-time
4. **Improves Over Time**: Multiple calibration sessions create a more accurate profile

**Accuracy Improvement**: 
- **Without Calibration**: ~50-100 pixel error (general model)
- **With Calibration**: ~20-50 pixel error (personalized model)
- **With Multiple Sessions**: ~10-30 pixel error (refined profile)

#### How to Use Calibration

**Step 1: Access Calibration**
- Open the app and navigate to the main screen
- Tap the **"New Calibration"** or **"Start Calibration"** button
- Choose your calibration mode:
  - **Grid Calibration** (Recommended for first-time users): Fixed points in a 3×3 or 5×5 grid
  - **Dynamic Calibration** (Advanced): Moving target that adapts to your screen

**Step 2: Prepare for Calibration**
- **Environment**: Use in good lighting with your face clearly visible
- **Position**: Hold your device at your normal viewing distance (20-30cm recommended)
- **Stability**: Keep your head relatively still during each point capture
- **Face Detection**: Ensure your face is fully visible in the camera frame

**Step 3: Complete the Calibration Process**

**For Grid Calibration:**
1. A target dot will appear at different screen locations (9 points for standard, 25 for detailed)
2. **Look directly at each dot** when it appears
3. The app will automatically capture data after a 3-second countdown
4. Keep your face visible and hold still during capture
5. Repeat for all points (takes ~2-3 minutes)

**For Dynamic Calibration:**
1. A moving target will appear on screen
2. **Follow the target with your eyes** as it moves
3. The app captures data continuously while tracking
4. Complete when you've covered enough screen area

**Step 4: Verify Calibration**
- After completion, the app saves your calibration session
- You can see your calibration count in the main screen
- **Multiple sessions improve accuracy** - consider calibrating 2-3 times for best results

**Step 5: Use Enhanced Gaze Tracking**
- Once calibrated, gaze predictions use your personal profile
- The app combines the general AI model with your calibration data
- Accuracy improves automatically without any additional steps

#### Calibration Tips & Best Practices

✅ **Do:**
- Calibrate in your typical usage environment (lighting, position)
- Hold the device the same way you normally use it
- Complete all points in one session without interruption
- Re-calibrate if you change devices or major environmental factors
- Perform multiple calibration sessions for better accuracy

❌ **Don't:**
- Move your head significantly during point capture
- Calibrate in poor lighting or with face partially obscured
- Rush through the process - take your time
- Calibrate while wearing different glasses than usual
- Interrupt the calibration process mid-session

#### Troubleshooting Calibration

**"Face Detection Lost" Warning:**
- Ensure your face is fully visible in the camera frame
- Improve lighting conditions
- Remove obstructions (hands, objects) from camera view
- Restart calibration if face detection fails repeatedly

**Low Accuracy After Calibration:**
- Try calibrating again - multiple sessions help
- Ensure consistent device positioning
- Check that lighting conditions match your usage
- Consider using detailed calibration (5×5 grid) instead of standard

**Calibration Not Saving:**
- Check app permissions (storage access may be required)
- Ensure stable internet connection if syncing to server
- Restart the app and try again

### What You Need to Do

**Prerequisites:**
- Android device running Android 7.0 (API 24) or higher
- Front-facing camera
- Emotiv BCI headset (optional, for full BCI control)
- Server component running (see server documentation)

**Setup Steps:**
1. **Install the APK** on your Android device
2. **Grant Permissions**: Allow camera, overlay, and sensor access when prompted
3. **Configure Server**: Enter your server URL in the app settings (if using BCI features)
4. **Calibrate Gaze** (Recommended): Complete at least one calibration session for improved accuracy
5. **Start Service**: Enable the background service to begin receiving BCI commands

**Important Notes:**
- The app processes all data locally (no cloud data transmission)
- Camera access is used only for gaze tracking, no images are stored
- Background service may be restricted by battery optimization—disable it for this app
- Calibration data is stored locally and can be synced to your server (optional)

### Known Issues & Limitations
- Gaze tracking accuracy depends on lighting conditions and device positioning
- First-time calibration required for optimal performance (app works without it, but with reduced accuracy)
- Battery usage is higher due to continuous camera and sensor usage
- Face detection may be affected by glasses, lighting, or extreme angles


