Functions
```c
// Add a function to watch a particular hint.
// name - the hint to watch.
// callback - An SDL_HintCallback function that will be called when the hint value changes.
// *userdata - a pointer to pass to the callback function.
void SDL_AddHintCallback(const char *name, SDL_HintCallback callback, void *userdata);

// Clear all hints.
void SDL_ClearHints(void);

// Remove a function watching a particular hint.
// name - the hint to watch.
// callback - An SDL_HintCallback function that will be called when the hint value changes.
// *userdata - a pointer to pass to the callback function.
void SDL_DelHintCallback(const char *name, SDL_HintCallback callback, void *userdata);

// Get the value of a hint.
// name - the hint to query.
// Return - string value of a hint or NULL if the hint isn't set.
const char * SDL_GetHint(const char *name);

// Get the boolean value of a hint variable.
// name - the name of the hint to get the boolean value from.
// default_value - the value to return if the hint does not exist.
// Return - boolean value of a hint or the provided default value if the hint does not exist.
SDL_bool SDL_GetHintBoolean(const char *name, SDL_bool default_value);

// Reset a hint to the default value.
// name - the hint to reset.
// Return - SDL_TRUE if the hint was set, SDL_FALSE otherwise.
SDL_bool SDL_ResetHint(const char *name);

// Reset all hints to the default values.
void SDL_ResetHints(void);

// Set a hint with normal priority.
// name - the hint to set.
// value - the value of the hint variable.
// Return - SDL_TRUE if the hint was set, SDL_FALSE otherwise.
SDL_bool SDL_SetHint(const char *name, const char *value);

// Set a hint with a specific priority.
// name - the hint to set.
// value - the value of the hint variable.
// priority - the SDL_HintPriority level for the hint.
// Return - SDL_TRUE if the hint was set, SDL_FALSE otherwise.
SDL_bool SDL_SetHintWithPriority(const char *name, const char *value, SDL_HintPriority priority);
```

Datatypes
```c
// Type definition of the hint callback function.
// userdata - what was passed as userdata to SDL_AddHintCallback().
// name - what was passed as name to SDL_AddHintCallback().
// oldValue - the previous hint value.
// newValue - the new value hint is to be set to.
typedef void (SDLCALL *SDL_HintCallback)(void *userdata, const char *name, const char *oldValue, const char *newValue);
```

Enums
```c
// An enumeration of hint priorities
typedef enum SDL_HintPriority
{
    SDL_HINT_DEFAULT,
    SDL_HINT_NORMAL,
    SDL_HINT_OVERRIDE
} SDL_HintPriority;
```

Macros
```c
// A variable controlling whether the Android / iOS built-in accelerometer should be listed as a joystick device.
// Default: True, The accelerometer is available as a 3 axis joystick
#define SDL_HINT_ACCELEROMETER_AS_JOYSTICK "SDL_ACCELEROMETER_AS_JOYSTICK"

// Specify the behavior of Alt+Tab while the keyboard is grabbed.
// Default: SDL will minimize your window when Alt+Tab is pressed
#define SDL_HINT_ALLOW_ALT_TAB_WHILE_GRABBED "SDL_ALLOW_ALT_TAB_WHILE_GRABBED"

// If set to "0" then never set the top most bit on a SDL Window, even if the video mode expects it.
// Default: allow topmost
#define SDL_HINT_ALLOW_TOPMOST "SDL_ALLOW_TOPMOST"

// Android APK expansion main file version.
// Default: this hint is not set and the APK expansion files are not searched.
#define SDL_HINT_ANDROID_APK_EXPANSION_MAIN_FILE_VERSION "SDL_ANDROID_APK_EXPANSION_MAIN_FILE_VERSION"

// Android APK expansion patch file version.
// Default: this hint is not set and the APK expansion files are not searched.
#define SDL_HINT_ANDROID_APK_EXPANSION_PATCH_FILE_VERSION "SDL_ANDROID_APK_EXPANSION_PATCH_FILE_VERSION"

// A variable to control whether the event loop will block itself when the app is paused.
// Default: Blocking
#define SDL_HINT_ANDROID_BLOCK_ON_PAUSE "SDL_ANDROID_BLOCK_ON_PAUSE"

// A variable to control whether SDL will pause audio in background (Requires SDL_ANDROID_BLOCK_ON_PAUSE as "Non blocking")
// Default: Paused
#define SDL_HINT_ANDROID_BLOCK_ON_PAUSE_PAUSEAUDIO "SDL_ANDROID_BLOCK_ON_PAUSE_PAUSEAUDIO"

// A variable to control whether we trap the Android back button to handle it manually.
// Default: Back button will be handled as usual for system.
#define SDL_HINT_ANDROID_TRAP_BACK_BUTTON "SDL_ANDROID_TRAP_BACK_BUTTON"

// Specify an application name.
// Default: probably the application's name or "SDL Application" if SDL doesn't have any better information.
#define SDL_HINT_APP_NAME "SDL_APP_NAME"

// Specify if SDL_RWFromFile should use the resource dir on Apple platforms.
// Default: SDL will use the app's resource directory
#define SDL_HINT_APPLE_RWFROMFILE_USE_RESOURCES "SDL_APPLE_RWFROMFILE_USE_RESOURCES"

// A variable controlling whether controllers used with the Apple TV generate UI events.
// Default: Controller input does not generate UI events
#define SDL_HINT_APPLE_TV_CONTROLLER_UI_EVENTS "SDL_APPLE_TV_CONTROLLER_UI_EVENTS"

// A variable controlling whether the Apple TV remote's joystick axes will automatically match the rotation of the remote.
// Default: Remote orientation does not affect joystick axes
#define SDL_HINT_APPLE_TV_REMOTE_ALLOW_ROTATION "SDL_APPLE_TV_REMOTE_ALLOW_ROTATION"

// A variable controlling the audio category on iOS and Mac OS X
// Default: "ambient": Use the AVAudioSessionCategoryAmbient audio category, will be muted by the phone mute switch
#define SDL_HINT_AUDIO_CATEGORY "SDL_AUDIO_CATEGORY"

// Specify an application name for an audio device.
// Default: this will be the name set with SDL_HINT_APP_NAME, if that hint is set. Otherwise, it'll probably the application's name or "SDL Application" if SDL doesn't have any better information.
#define SDL_HINT_AUDIO_DEVICE_APP_NAME "SDL_AUDIO_DEVICE_APP_NAME"

// Specify an application name for an audio device.
// Default: "audio stream" or something similar.
#define SDL_HINT_AUDIO_DEVICE_STREAM_NAME "SDL_AUDIO_DEVICE_STREAM_NAME"

// Specify an application role for an audio device.
// Default: "Game" or something similar.
#define SDL_HINT_AUDIO_DEVICE_STREAM_ROLE "SDL_AUDIO_DEVICE_STREAM_ROLE"

// A variable that causes SDL to not ignore audio "monitors"
// Default: "0", SDL ignores audio devices that aren't associated with physical hardware.
#define SDL_HINT_AUDIO_INCLUDE_MONITORS "SDL_AUDIO_INCLUDE_MONITORS"

// A variable controlling speed/quality tradeoff of audio resampling.
// Default: "0" or "default": Use SDL's internal resampling (Default when not set - low quality, fast)
#define SDL_HINT_AUDIO_RESAMPLING_MODE "SDL_AUDIO_RESAMPLING_MODE"

// A variable that decides what audio backend to use.
// Default: unset, SDL will try all available audio backends in a reasonable order until it finds one that can work
#define SDL_HINT_AUDIODRIVER "SDL_AUDIODRIVER"

// A variable controlling whether SDL updates joystick state when getting input events
// "1": SDL will automatically call SDL_JoystickUpdate()
#define SDL_HINT_AUTO_UPDATE_JOYSTICKS  "SDL_AUTO_UPDATE_JOYSTICKS"

// A variable controlling whether SDL updates sensor state when getting input events
// "1": SDL will automatically call SDL_SensorUpdate()
#define SDL_HINT_AUTO_UPDATE_SENSORS "SDL_AUTO_UPDATE_SENSORS"

// Prevent SDL from using version 4 of the bitmap header when saving BMPs.
// Default: "0": Surfaces with a colorkey or an alpha channel are saved to a 32-bit BMP file with an alpha mask. SDL will use the bitmap header version 4 and set the alpha mask accordingly.
#define SDL_HINT_BMP_SAVE_LEGACY_FORMAT "SDL_BMP_SAVE_LEGACY_FORMAT"

// A variable that lets you disable the detection and use of DirectInput gamepad devices
// Default: "1": Enable DirectInput detection
#define SDL_HINT_DIRECTINPUT_ENABLED "SDL_DIRECTINPUT_ENABLED"

// Override for SDL_GetDisplayUsableBounds()
// Default: ??? (unset)
#define SDL_HINT_DISPLAY_USABLE_BOUNDS "SDL_DISPLAY_USABLE_BOUNDS"

// Disable giving back control to the browser automatically when running with asyncify
// Default: "1": Enable emscripten_sleep calls
#define SDL_HINT_EMSCRIPTEN_ASYNCIFY   "SDL_EMSCRIPTEN_ASYNCIFY"

// Override the binding element for keyboard inputs for Emscripten builds
// Default: "#window": the javascript window object
#define SDL_HINT_EMSCRIPTEN_KEYBOARD_ELEMENT "SDL_EMSCRIPTEN_KEYBOARD_ELEMENT"

// A variable that controls whether the on-screen keyboard should be shown when text input is active
// Default: "1": Show the on-screen keyboard
#define SDL_HINT_ENABLE_SCREEN_KEYBOARD "SDL_ENABLE_SCREEN_KEYBOARD"

// A variable that controls whether Steam Controllers should be exposed using the SDL joystick and game controller APIs
// "1": Scan for Steam Controllers
#define SDL_HINT_ENABLE_STEAM_CONTROLLERS "SDL_ENABLE_STEAM_CONTROLLERS"

// A variable controlling verbosity of the logging of SDL events pushed onto the internal queue.
// "0": Don't log any events
#define SDL_HINT_EVENT_LOGGING   "SDL_EVENT_LOGGING"

// A variable controlling whether raising the window should be done more forcefully
// "0": No forcing
#define SDL_HINT_FORCE_RAISEWINDOW "SDL_HINT_FORCE_RAISEWINDOW"

// A variable controlling how 3D acceleration is used to accelerate the SDL screen surface.
// Default: SDL tries to make a best guess for each platform whether to use acceleration or not.
#define SDL_HINT_FRAMEBUFFER_ACCELERATION "SDL_FRAMEBUFFER_ACCELERATION"

// A variable containing a list of devices to skip when scanning for game controllers.
// Default: ???
#define SDL_HINT_GAMECONTROLLER_IGNORE_DEVICES "SDL_GAMECONTROLLER_IGNORE_DEVICES"

// If set, all devices will be skipped when scanning for game controllers except for the ones listed in this variable.
// Default: ???
#define SDL_HINT_GAMECONTROLLER_IGNORE_DEVICES_EXCEPT "SDL_GAMECONTROLLER_IGNORE_DEVICES_EXCEPT"


// If set, game controller face buttons report their values according to their labels instead of their positional layout.
// Default: "1": Report the face buttons by label instead of position
#define SDL_HINT_GAMECONTROLLER_USE_BUTTON_LABELS "SDL_GAMECONTROLLER_USE_BUTTON_LABELS"

// A variable that lets you manually hint extra gamecontroller db entries.
// ???
#define SDL_HINT_GAMECONTROLLERCONFIG "SDL_GAMECONTROLLERCONFIG"

// A variable that lets you provide a file with extra gamecontroller db entries.
// ??
#define SDL_HINT_GAMECONTROLLERCONFIG_FILE "SDL_GAMECONTROLLERCONFIG_FILE"

// A variable that overrides the automatic controller type detection
// ???
#define SDL_HINT_GAMECONTROLLERTYPE "SDL_GAMECONTROLLERTYPE"

// A variable controlling whether grabbing input grabs the keyboard
// SDL will not grab the keyboard so system shortcuts still work.
#define SDL_HINT_GRAB_KEYBOARD "SDL_GRAB_KEYBOARD"

// A variable containing a list of devices to ignore in SDL_hid_enumerate()
// ???
#define SDL_HINT_HIDAPI_IGNORE_DEVICES "SDL_HIDAPI_IGNORE_DEVICES"

// A variable controlling whether the idle timer is disabled on iOS.
// ???
#define SDL_HINT_IDLE_TIMER_DISABLED "SDL_IOS_IDLE_TIMER_DISABLED"

// A variable to control whether certain IMEs should handle text editing internally instead of sending SDL_TEXTEDITING events.
// "0": SDL_TEXTEDITING events are sent, and it is the application's responsibility to render the text from these events and differentiate it somehow from committed text.
#define SDL_HINT_IME_INTERNAL_EDITING "SDL_IME_INTERNAL_EDITING"

// A variable to control whether certain IMEs should show native UI components (such as the Candidate List) instead of suppressing them.
// "0": Native UI components are not display
#define SDL_HINT_IME_SHOW_UI "SDL_IME_SHOW_UI"

// A variable to control if extended IME text support is enabled.
// "0": Legacy behavior. Text can be truncated, no heap allocations. 
#define SDL_HINT_IME_SUPPORT_EXTENDED_TEXT "SDL_IME_SUPPORT_EXTENDED_TEXT"

// A variable controlling whether the home indicator bar on iPhone X should be hidden.
// "0": The indicator bar is not hidden (default for windowed applications)
// "2": The indicator bar is dim and the first swipe makes it visible and the second swipe performs the "home" action (default for fullscreen applications)
#define SDL_HINT_IOS_HIDE_HOME_INDICATOR "SDL_IOS_HIDE_HOME_INDICATOR"


```
