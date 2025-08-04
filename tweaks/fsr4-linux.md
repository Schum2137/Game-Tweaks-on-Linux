# FSR 4 Upgrade for Games Using FSR 3.1

You can force games with FSR 3.1 to use FSR 4 by using `proton-cachyos` or `proton-ge` and `Mesa 25.2+`.  
This has been tested and confirmed working in **Grand Theft Auto V** on an **RX 9070 XT**.

## ✅ Fix Steps

1. Ensure you're using a game that supports **FSR 3.1**
2. In Steam, set the Proton version to **proton-cachyos** or **proton-ge**
3. Add the following to the game’s **launch options**:
**PROTON_FSR4_UPGRADE=1 %command%**

FSR 3.1 will now be replaced with **FSR 4** during runtime.

## ⚠️ **RDNA3 (e.g., RX 7000 series)**

You can try:
DXIL_SPIRV_CONFIG=wmma_rdna3_workaround PROTON_FSR4_UPGRADE=1 %command%

## 📌 Notes

- Requires `proton-cachyos` or `proton-ge` and `Mesa 25.2` or newer
- Game must already use FSR 3.1 for the upgrade to apply
- Not guaranteed to work on all RDNA3 GPUs — test per title


# FSR 4 Upgrade via OptiScaler

This method allows you to upgrade to FSR 4 in any supported game using **OptiScaler**.  
Works even in titles without native FSR 3.1, as long as OptiScaler can hook into the rendering pipeline.

## ✅ Fix Steps

1. Download the latest **OptiScaler Nightly** build from:  
   https://github.com/optiscaler/OptiScaler/releases/tag/nightly

2. Extract **all files** into the same folder as the game’s `.exe`

   > 🔴 **Important:** For Unreal Engine games, the `.exe` is typically located in a subfolder like:  
   > `<Game>\GameName\Binaries\Win64` or `WinGDK\`  
   >  
   > Example paths:  
   > `Expedition 33\Sandfall\Binaries\Win64`  
   > `Jedi Survivor\SwGame\Binaries\Win64`  
   > `Cyberpunk 2077\bin\x64`  
   > `HITMAN 3\Retail`  
   > `Warhammer 40,000 DARKTIDE\binaries`  
   > `The Witcher 3\bin\x64_dx12`

3. Run the `setup_linux.sh` script included with OptiScaler.

4. Launch the game.

5. Press `Insert` in-game to open the OptiScaler overlay.

6. Select **FSR 4** from the scaling options.

## 📌 Notes

- This method works regardless of whether the game has native FSR 3.1 or not
- ⚠️ OptiScaler is recommended to be used for single player games, as it can trigger an anti-cheat. Use it at your own risk
