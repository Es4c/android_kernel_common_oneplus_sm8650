### It WILL cause bootloop, do not flash!

## Difference between this fork and original repo?
I updated bbr v1 to bbr v3 with "__bpf_kfunc" being removed from tcp_bbr functions as the kernel itself doesn't support it (definition missing in bpf.h).

Gemini says "The BBR algorithm's core functionality is self-contained within the kernel and does not rely on BPF. The BPF-related code is an optional interface provided for advanced users who want to programmatically debug, monitor, or customize the algorithm's behavior. If you don't need these advanced capabilities, you can safely ignore the BPF-related parts of the code". So, I suppose it is safe to remove "__bpf_kfunc".

The code for updating bbr is cherry-picked from [zen-kernel](https://github.com/zen-kernel/zen-kernel/commit/bcb27e4adacda606c76349bfba3305db6ea83887), and refered to [xiaomi_xaga_kernel](https://github.com/ferstar/xiaomi_xaga_kernel/tree/mglru) for some bug-fixes..

