# Quote:

">Ethereum Community Forum
>
>[1080 Specific Ethereum Mining Issues 100](https://web.archive.org/web/20200927081915/https://forum.ethereum.org/discussion/9277/1080-specific-ethereum-mining-issues) - [original](https://forum.ethereum.org/discussion/9277/1080-specific-ethereum-mining-issues)
>This thread is an attempt to summarize and discuss GTX 1080 specific issues.
>
>
>Though you won’t like it."

-from: https://forums.developer.nvidia.com/t/how-to-force-performance-level-3-driver-381-22-with-gtx-1080-ti/50353/12


# Quote:

"Normz
Jun 25 '17
Actually I discovered that the same problem exist in Windows and also for both GTX 1080 Ti and GTX 1070 (I tested 15 different cards) … it’s either that the new Pascal architecture no longer allows forcing the high performance state, or it’s driver bug across all OSs. The crypto-mining community has discovered this aspect a while ago.

Forcing the P state was working just fine in the GTX 9xx series. Why did Nvidia change this?

Essentially, Nvidia currently forces us to run the cards in a semi-crippled state. You can try overclock the P2 clock offsets to give the same clocks as the ones P3 has (which are usually about 1000 MHz higher for 1080 Ti), but you must do it while in P2 and it’s then almost guaranteed to crash once it exits P2. That is because you can’t change only the P2 clock offsets; when you change the P2 clock offsets, the P3 ones change as well by the same amount, going beyond the limit of P3; so when the card exits P2 (e.g. every time your 3D application finishes or has a lower load) then it will cycle out of P2 and at some point will get to P3 and then crash.

I was never able to control that behavior. Neither under Linux, nor under Windows. I would also be happy if I could tell it to never go to P3, and then keep P2 overclocked. But that’s not possible either.

It seems the 10xx cards are always in adaptive mode, regardless of you specifying “performance mode” in nvidia-settings. It cycles P states according to some unknown algorithm, e.g. it goes to P3 sporadically when semi-idle, but never when fully loaded.

How can we get an official response to this from Nvidia, to see if it’s a bug or intended behavior, or if there is any way to achieve what we want?

p.s. The nomenclature is also confusing, because most refer to the performance state as P0, whereas at least in Linux that’s labeled P3."

-from: https://forums.developer.nvidia.com/t/how-to-force-performance-level-3-driver-381-22-with-gtx-1080-ti/50353/20
