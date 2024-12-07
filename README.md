# avchd-export

## About

This is a bash script to export **MTS files** from AVCHD and convert them to **MP4** or other formats using different codec combinations. It requires **FFmpeg** for the conversion process. This script loops through all MTS files in a specified directory and converts them using your chosen preset configuration.

**Note**: This solution is designed for **macOS** only!

## The Easy Way

Watch the YouTube video for instructions on how to install and use the `avchd-export.sh` script:  
<https://www.youtube.com/watch?v=bA875TJR0Zs>

## Installation

1. **Download FFmpeg** from: [https://evermeet.cx/ffmpeg/](https://evermeet.cx/ffmpeg/)  
   Or, if you prefer: [https://ffmpeg.org/download.html#build-mac](https://ffmpeg.org/download.html#build-mac)  
   - Click the Apple icon and choose "Static builds for macOS 64-bit."

2. Download either the **release** or **snapshot** version as a DMG.

3. Create a new directory called **"FFMPEG"** in your **Applications** directory:  
   - Open the DMG file and drag the `ffmpeg` binary into `/Applications/FFMPEG/`.  
   - The path to FFmpeg should be: `/Applications/FFMPEG/ffmpeg`.

4. Download the `avchd-export.sh` script to your desired location.

5. If you placed FFmpeg in a different location, update the `FFMPEG` variable in the script accordingly (see the comments in the script).

## Usage

The script is executed as:

```bash
./avchd-export.sh [input directory] [optional: output directory] [optional: preset]

### Available Presets

| **Preset**     | **Description**                                     |
|----------------|-----------------------------------------------------|
| `h264_aac`    | H.264 video + AAC audio (MP4, general-purpose)      |
| `h265_aac`    | H.265/HEVC video + AAC audio (MP4, high-efficiency) |
| `vp9_opus`    | VP9 video + Opus audio (WebM, web streaming)        |
| `prores_pcm`  | ProRes video + PCM audio (MOV, professional editing)|
| `h264_ac3`    | H.264 video + AC3 audio (MKV, surround sound)       |

### Examples

1. **Basic Conversion (Default Preset: `h264_aac`)**:

   ```bash
   ./avchd-export.sh /path/to/input

1. **Specify an Output Directory:**:

   ```bash
   ./avchd-export.sh /path/to/input /path/to/output

1. **Specify a Preset:**:

   ```bash
   ./avchd-export.sh /path/to/input /path/to/output h265_aac

1. **Full Example:**:

   ```bash
   ./avchd-export.sh /Volumes/SDCARD/PRIVATE/AVCHD/BDMV/STREAM ~/Desktop/avchd-output vp9_opus

## Step-by-Step Instructions

1. **Locate Your MTS Files**:  
   - Insert the SD card into your Mac.  
   - Navigate to the MTS files:  
     - Go to `PRIVATE` → Right-click `AVCHD` → Show Package Contents.  
     - Right-click `BDMV` → Show Package Contents.  
     - Open the `STREAM` folder. You should see `.MTS` files.

2. **Open a Terminal**:  
   - Go to **Applications** → **Utilities** → **Terminal**.  
   - Navigate to the directory where you saved the `avchd-export.sh` script.

3. **Run the Script**:  
   - Type `./avchd-export.sh` and drag the folder containing your MTS files into the terminal:

     ```bash
     ./avchd-export.sh /Volumes/SDCARD/PRIVATE/AVCHD/BDMV/STREAM
     ```

4. **Optional Parameters**:  
   - Add an output directory and a preset if desired:

     ```bash
     ./avchd-export.sh /Volumes/SDCARD/PRIVATE/AVCHD/BDMV/STREAM ~/Desktop/output h265_aac
     ```

5. **Execute the Script**:  
   - Press **Enter** to start the conversion.  
   - Wait for the conversion to complete.

6. **Check the Output**:  
   - The converted files will be in the specified output directory (default: `avchd-export`).  
   - Log messages will be saved to `avchd-export.log` in the output directory.

## Notes

- **Default Preset**: If no preset is specified, the script defaults to `h264_aac` (H.264 video + AAC audio).
- **Logging**: Conversion logs are stored in `avchd-export.log` in the output directory.
- **Compatibility**: The generated files are compatible with most modern devices and platforms.

Enjoy converting your AVCHD files! 🎥
