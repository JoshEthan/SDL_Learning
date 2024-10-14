```c
// Initialize the SDL library.
// flags - subsystem initialization flags.
//      SDL_INIT_TIMER: timer subsystem
//      SDL_INIT_AUDIO: audio subsystem
//      SDL_INIT_VIDEO: video subsystem; automatically initializes the events subsystem
//      SDL_INIT_JOYSTICK: joystick subsystem; automatically initializes the events subsystem
//      SDL_INIT_HAPTIC: haptic (force feedback) subsystem
//      SDL_INIT_GAMECONTROLLER: controller subsystem; automatically initializes the joystick subsystem
//      SDL_INIT_EVENTS: events subsystem
//      SDL_INIT_EVERYTHING: all of the above subsystems
//      SDL_INIT_NOPARACHUTE: compatibility; this flag is ignored
// Return - 0 on success or a negative error code on failure.
int SDL_Init(Uint32 flags);

// Compatibility function to initialize the SDL library.
// flags - any of the flags used by SDL_Init().
// Return - 0 on success or a negative error code on failure.
int SDL_InitSubSystem(Uint32 flags);

// Clean up all initialized subsystems.
void SDL_Quit(void);

// Shut down specific SDL subsystems.
// flags - any of the flags used by SDL_Init().
void SDL_QuitSubSystem(Uint32 flags);

// Get a mask of the specified subsystems which are currently initialized.
// flags - any of the flags used by SDL_Init(); see SDL_Init for details.
// Return- a mask of all initialized subsystems if flags is 0, otherwise it returns the initialization status of the specified subsystems.
Uint32 SDL_WasInit(Uint32 flags);
```
