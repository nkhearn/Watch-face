# Doomguy Watch Face

A Wear OS watch face featuring the iconic Doomguy, whose health status reflects your watch's battery level. Built using the [Watch Face Format (WFF)](https://developer.android.com/training/wearables/wff).

| Screenshot |
| :---: |
| <img src="./screenshots/Screenshot_20260627-091742.png" alt="Doomguy Watch Face" width="200"/> |

## Features

- **Digital Clock**: 24-hour format with AM/PM and seconds display.
- **Date Display**: Current day of the week and day of the month.
- **Doomguy Battery Indicator**: Doomguy's face changes based on your battery percentage:
    - **Healthy (80-100%)**: Doomguy is ready for action.
    - **Hurt (50-80%)**: Doomguy has taken some damage.
    - **Dying (20-50%)**: Doomguy is in critical condition.
    - **Dead (0-20%)**: Doomguy is down.
- **Battery Percentage**: Numeric display of current battery level.
- **Heart Rate**: Real-time heart rate monitoring (BPM).

## Project Structure

This project uses a preprocessor to generate the final Watch Face Format XML.

- `watchface-pp.xml`: The source template for the watch face logic.
- `doomguy/`: The Android project module containing assets and configuration.
- `xml-preprocessor/`: Tooling used to process the XML template.

## Getting Started

### Prerequisites

- Android Studio or Gradle
- Python 3 (for the XML preprocessor)

### Building

To build the debug APK, run:

```bash
./gradlew assembleDebug
```

The resulting APK will be located in `doomguy/build/outputs/apk/debug/`.

### Preprocessing the XML

The final watch face XML is generated from `watchface-pp.xml`. If you make changes to the template, you can regenerate the output using:

```bash
python3 xml-preprocessor/preprocess.py watchface-pp.xml doomguy/src/main/res/raw/watchface.xml -y
```

## Dependencies

This project relies on the following components as specified in `clockwork.yml`:

- [XML Preprocessor](https://github.com/Turtlepaw/xml-preprocessor)
- [Example UI Package](https://github.com/WearOSCommunity/example-ui-pkg)

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.
