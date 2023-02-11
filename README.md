
#### Why `MutexGuard` is not `Send`? 
#rust 

I want to send `MutexGuard` (`parking_lot` version) to a thread but the rust compiler is not allowing me to do that. Then I found that this is deliberate and documented [here](https://github.com/rust-lang/rust/issues/23465#issuecomment-82730326).
>If a thread attempts to unlock a mutex that it has not locked or a mutex which is unlocked, undefined behavior results.
