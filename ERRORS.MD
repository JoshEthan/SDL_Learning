```c
// Clear any previous error message for this thread.
void SDL_ClearError(void);

// Retrieve a message about the last error that occurred on the current thread.
// Return - A message with information about the specific error that occurred, or an empty string if there hasn't been an error message set since the last call to SDL_ClearError().
const char* SDL_GetError(void);

// Get the last error message that was set for the current thread.
// errstr - A buffer to fill with the last error message that was set for the current thread.
// maxlen - The size of the buffer pointed to by the errstr parameter.
// Return - The pointer passed in as the errstr parameter.
char * SDL_GetErrorMsg(char *errstr, int maxlen);

// Set the SDL error message for the current thread.
// fmt - a printf()-style message format string.
// ... - additional parameters matching % tokens in the fmt string, if any.
// Return - -1.
int SDL_SetError(const char *fmt, ...);
```
