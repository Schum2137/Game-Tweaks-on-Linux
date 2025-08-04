# 🛠️ FSR Frame Generation Fix for Proton (Linux)
A simple workaround for fixing **FSR Frame Generation** in games running under **Proton/Wine** on Linux systems, caused by missing **hardware scheduling** support in the Windows registry emulation.

Currently confirmed working for:
- ✅ **Stellar Blade**

## ⚙️ The Issue
A recent update broke **FSR Frame Gen** support under Proton, even when the hardware supports it (e.g., RX 6800, RX 7900, RX 9070 XT). This is due to **hardware scheduling** being disabled by default in the Windows registry inside the Wine/Proton prefix.

## ✅ The Fix (via Protontricks + regedit)
1. Open `Protontricks`  
   → Select your game (e.g., **Stellar Blade**)  
   → Choose the **default wineprefix**  
2. Launch `regedit`  
3. Navigate to:  
   `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\`  
4. Create a new key (if missing):  
   `GraphicsDrivers`  
5. Inside `GraphicsDrivers`, create a new **DWORD (32-bit)** value:  
   `Name: HwSchMode`  
   `Value: 2`  
6. Close `regedit` and launch the game.

FSR Frame Generation should now work again.

## 📌 Notes
- This method assumes your GPU **supports hardware scheduling** (most AMD GPUs from RX 5600 and up do).  
- The registry edit only affects the selected Proton/Wine prefix and won’t affect your system globally.  
- Tested with:  
  - Proton-CachyOS  
  - AMD RX 9070 XT on CachyOS
