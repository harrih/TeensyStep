# Detailed Commit Comparison

## Recent Commits in improveCallback Branch (Top 50 of 279)

| Commit | Author | Date | Message |
|--------|--------|------|---------|
| dcdb0ee | luni64 | 3 years, 6 months ago | activated speed override |
| 6db682c | luni64 | 3 years, 6 months ago | changed step ISR to invoke callback AFTER last pulse |
| 2fd0049 | luni64 | 3 years, 8 months ago | Merge pull request #136 from bimac/master |
| c10de78 | Florian Rau | 3 years, 8 months ago | add definition of static constexpr members |
| cd4bd9e | luni64 | 3 years, 10 months ago | bump version |
| d32ff53 | luni64 | 3 years, 10 months ago | changed std::abs to abs to escape the Arduino madness |
| 1f68646 | luni64 | 4 years ago | Merge pull request #126 from luni64/RotateCallback |
| e151a87 | luni64 | 4 years ago | Added callback functionality to RotateControl |
| 29d9318 | luni64 | 4 years, 2 months ago | Merge pull request #120 from luni64/develop |
| 9efde61 | luni64 | 4 years, 2 months ago | Bump version to 2.3.1 |
| d1fd0bd | luni64 | 4 years, 2 months ago | Fix issue with uint32_t overflow for large speed / acceleration values |
| 1275433 | luni64 | 4 years, 2 months ago | Fix bug preventing restart after overrideSpeed(0) |
| 615d5fc | luni64 | 4 years, 4 months ago | bump version |
| 15380e9 | luni64 | 4 years, 4 months ago | Merge pull request #113 from luni64/develop |
| 07ba4db | luni64 | 4 years, 4 months ago | Fixes issue stopping motor when no steps are left |
| 7d1a0bf | luni64 | 4 years, 7 months ago | Optimize speed of motor group in case v_max |
| 57e532f | luni64 | 5 years ago | Merge pull request #79 from ramboerik/fix-stm32f4-too-long-first-pulse |
| cfb50b0 | Erik tideman | 5 years ago | Keep interrupt register force update for stm32f4 to speed up startup time |
| 8f66022 | Erik tideman | 5 years ago | Fix first pulse being too long as the pulse's interval wasn't loaded correctly |
| 0e9d47d | luni64 | 5 years ago | Merge pull request #75 from ramboerik/feature-stm32f4 |
| 64791f8 | Erik Tideman | 5 years ago | Removed test files |
| e5b6d6d | Erik tideman | 5 years ago | Cleanup of arduino headers inclusion |
| f06b82e | Erik tideman | 5 years ago | Fixed defines for platform teensy4 |
| d956a52 | Erik tideman | 5 years ago | Changed to use platform defines that works for all teensy3 versions |
| be1cb80 | Erik Tideman | 5 years ago | Cleaned up repo |
| 719cd6f | Erik Tideman | 5 years ago | removed esp32 code with unknown status |
| e1e105a | Erik tideman | 5 years ago | Added guards for teensy3's PIT.cpp to prevent it from being compiled for stm32 |
| 8aaa5d2 | Erik tideman | 5 years ago | Minor comment cleanup |
| e701229 | Erik tideman | 5 years ago | Merge branch 'master' into feature-stm32f4 |
| 06c0eab | luni64 | 6 years ago | Update README.md |
| 55f01e6 | luni64 | 6 years ago | Bump version to 2.1 |
| b9dec74 | luni64 | 6 years ago | Merge branch 'DevTimer' |
| 70a0498 | luni64 | 6 years ago | Merge branch 'hotfix/GCC9_Compatibility' |
| bc65ad5 | luni64 | 6 years ago | Make linker happy |
| f3e6b6f | luni64 | 6 years ago | Fixed overflow problem in speed calculation |
| 00100ec | luni64 | 6 years ago | Compatibility to more modern compilers (GCC9+) |
| 5d30fd0 | Erik tideman | 6 years ago | Added ifdef to prevent main from being built when used as library |
| 23b51cb | Erik tideman | 6 years ago | reapplied patch to override setTargetAbs/setTargetRel |
| c9b9b74 | Erik tideman | 6 years ago | Adjusted what timers to use |
| f904e4f | Erik tideman | 6 years ago | Added functionality for stm32 to pick timers by itself |
| 985e63f | Erik tideman | 6 years ago | Updated README, library.json |
| 73e8196 | Erik tideman | 6 years ago | Added ifdef guards to make it possible to build library for multiple targets |
| 6509705 | Erik tideman | 6 years ago | Added example of known bug in the second triggered interrupt |
| bbb9da7 | Erik tideman | 6 years ago | Added documentation |
| c7c24a1 | Erik tideman | 6 years ago | Added force update on accelerator interrupt start |

...and 229 more commits

## Key Contributors

- **luni64**: Primary maintainer, majority of commits
- **Erik Tideman/Erik tideman**: Major contributor, especially for STM32 support
- **Florian Rau**: Static constexpr members fix

## Major Themes in improveCallback Branch

1. **Callback System Improvements** (Most Recent)
   - Activated speed override
   - Changed step ISR to invoke callback AFTER last pulse
   - Added callback functionality to RotateControl

2. **Bug Fixes**
   - Fixed uint32_t overflow for large speed/acceleration values
   - Fixed bug preventing restart after overrideSpeed(0)
   - Fixed issue stopping motor when no steps are left
   - Fixed first pulse timing issues for STM32F4

3. **Platform Support**
   - Extensive STM32F4 support
   - Teensy3/Teensy4 compatibility improvements
   - ESP32 support (later removed)

4. **Compiler Compatibility**
   - GCC9+ compatibility fixes
   - Static constexpr member definitions
   - std::abs vs Arduino abs conflict resolution

5. **Performance Optimizations**
   - Optimized motor group speed
   - Improved interrupt timing
   - Timer scheme improvements

## Version History in improveCallback

- **v2.3.2**: Latest version with speed override and callback improvements
- **v2.3.1**: Bug fixes for overflow and speed override
- **v2.3.0**: Motor stopping and speed optimization fixes
- **v2.2.0**: STM32F4 support
- **v2.1.0**: DevTimer improvements
- **V2.0.0**: Major version release
- **V1.0.0**: Initial major version
