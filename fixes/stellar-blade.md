# Stellar Blade — FSR Frame Generation Fix

Recent update broke FSR Frame Gen due to missing hardware scheduling in Wine/Proton.

## ✅ Fix (via Protontricks + regedit)

1. Open `Protontricks` → Select **Stellar Blade** → Choose **default wineprefix**
2. Run `regedit`
3. Go to: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\`
4. Create key: `GraphicsDrivers`
5. Inside it, create DWORD (32-bit): `HwSchMode`
6. Set value to: `2`
7. Close regedit and launch the game

✅ FSR Frame Generation should now work.

## 🧪 Tested On

- AMD RX 9070 XT
- Proton-CachyOS
