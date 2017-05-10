i is Mapper containers  
j is Reducer containers  
k is Container memory  
  
The below are the fastest parameter, and all duration are 19s.
  
i=1	j=4	k=512  
i=4	j=8	k=512  
i=6	j=2	k=512  
i=6	j=8	k=1024  
    
The below are the slowest parameter, and all duration are 23s.
  
i=6	j=4	k=512
  

The below are detail:
```  
Testing loop started on Wed May 10 04:17:57 UTC 2017
  
i=1,j=1,k=512,Testing loop started on Wed May 10 04:17:57 UTC 2017
  

  
real	0m12.764s
  
user	0m5.892s
  
sys	0m0.783s
  

  
real	0m3.132s
  
user	0m3.600s
  
sys	0m0.542s
  
rm: `/results/tg-10GB-1-1-512': No such file or directory
  
rm: `/results/ts-10GB-1-1-512': No such file or directory
  
i=1,j=1,k=512,Testing loop ended on Wed May 10 04:18:19 UTC 2017
  
i=1,j=1,k=1024,Testing loop started on Wed May 10 04:18:19 UTC 2017
  

  
real	0m12.805s
  
user	0m5.773s
  
sys	0m0.758s
  

  
real	0m2.988s
  
user	0m3.613s
  
sys	0m0.507s
  
rm: `/results/tg-10GB-1-1-1024': No such file or directory
  
rm: `/results/ts-10GB-1-1-1024': No such file or directory
  
i=1,j=1,k=1024,Testing loop ended on Wed May 10 04:18:41 UTC 2017
  
i=1,j=2,k=512,Testing loop started on Wed May 10 04:18:41 UTC 2017
  

  
real	0m12.647s
  
user	0m5.875s
  
sys	0m0.677s
  

  
real	0m3.079s
  
user	0m3.602s
  
sys	0m0.507s
  
rm: `/results/tg-10GB-1-2-512': No such file or directory
  
rm: `/results/ts-10GB-1-2-512': No such file or directory
  
i=1,j=2,k=512,Testing loop ended on Wed May 10 04:19:03 UTC 2017
  
i=1,j=2,k=1024,Testing loop started on Wed May 10 04:19:03 UTC 2017
  

  
real	0m11.618s
  
user	0m5.588s
  
sys	0m0.705s
  

  
real	0m3.210s
  
user	0m3.782s
  
sys	0m0.511s
  
rm: `/results/tg-10GB-1-2-1024': No such file or directory
  
rm: `/results/ts-10GB-1-2-1024': No such file or directory
  
i=1,j=2,k=1024,Testing loop ended on Wed May 10 04:19:24 UTC 2017
  
i=1,j=4,k=512,Testing loop started on Wed May 10 04:19:24 UTC 2017
  

  
real	0m10.631s
  
user	0m5.904s
  
sys	0m0.660s
  

  
real	0m3.065s
  
user	0m3.619s
  
sys	0m0.559s
  
rm: `/results/tg-10GB-1-4-512': No such file or directory
  
rm: `/results/ts-10GB-1-4-512': No such file or directory
  
i=1,j=4,k=512,Testing loop ended on Wed May 10 04:19:43 UTC 2017
  
i=1,j=4,k=1024,Testing loop started on Wed May 10 04:19:43 UTC 2017
  

  
real	0m12.798s
  
user	0m6.182s
  
sys	0m0.679s
  

  
real	0m3.039s
  
user	0m3.652s
  
sys	0m0.528s
  
rm: `/results/tg-10GB-1-4-1024': No such file or directory
  
rm: `/results/ts-10GB-1-4-1024': No such file or directory
  
i=1,j=4,k=1024,Testing loop ended on Wed May 10 04:20:05 UTC 2017
  
i=1,j=6,k=512,Testing loop started on Wed May 10 04:20:05 UTC 2017
  

  
real	0m11.913s
  
user	0m6.888s
  
sys	0m0.804s
  

  
real	0m2.996s
  
user	0m3.619s
  
sys	0m0.536s
  
rm: `/results/tg-10GB-1-6-512': No such file or directory
  
rm: `/results/ts-10GB-1-6-512': No such file or directory
  
i=1,j=6,k=512,Testing loop ended on Wed May 10 04:20:26 UTC 2017
  
i=1,j=6,k=1024,Testing loop started on Wed May 10 04:20:26 UTC 2017
  

  
real	0m11.765s
  
user	0m5.887s
  
sys	0m0.681s
  

  
real	0m3.110s
  
user	0m3.600s
  
sys	0m0.541s
  
rm: `/results/tg-10GB-1-6-1024': No such file or directory
  
rm: `/results/ts-10GB-1-6-1024': No such file or directory
  
i=1,j=6,k=1024,Testing loop ended on Wed May 10 04:20:47 UTC 2017
  
i=1,j=8,k=512,Testing loop started on Wed May 10 04:20:47 UTC 2017
  

  
real	0m10.470s
  
user	0m5.790s
  
sys	0m0.672s
  

  
real	0m3.133s
  
user	0m3.632s
  
sys	0m0.540s
  
rm: `/results/tg-10GB-1-8-512': No such file or directory
  
rm: `/results/ts-10GB-1-8-512': No such file or directory
  
i=1,j=8,k=512,Testing loop ended on Wed May 10 04:21:07 UTC 2017
  
i=1,j=8,k=1024,Testing loop started on Wed May 10 04:21:07 UTC 2017
  

  
real	0m10.817s
  
user	0m6.057s
  
sys	0m0.802s
  

  
real	0m3.046s
  
user	0m3.597s
  
sys	0m0.524s
  
rm: `/results/tg-10GB-1-8-1024': No such file or directory
  
rm: `/results/ts-10GB-1-8-1024': No such file or directory
  
i=1,j=8,k=1024,Testing loop ended on Wed May 10 04:21:27 UTC 2017
  
i=2,j=1,k=512,Testing loop started on Wed May 10 04:21:27 UTC 2017
  

  
real	0m12.789s
  
user	0m5.846s
  
sys	0m0.750s
  

  
real	0m3.101s
  
user	0m3.700s
  
sys	0m0.542s
  
rm: `/results/tg-10GB-2-1-512': No such file or directory
  
rm: `/results/ts-10GB-2-1-512': No such file or directory
  
i=2,j=1,k=512,Testing loop ended on Wed May 10 04:21:48 UTC 2017
  
i=2,j=1,k=1024,Testing loop started on Wed May 10 04:21:48 UTC 2017
  

  
real	0m11.752s
  
user	0m5.804s
  
sys	0m0.676s
  

  
real	0m2.979s
  
user	0m3.661s
  
sys	0m0.498s
  
rm: `/results/tg-10GB-2-1-1024': No such file or directory
  
rm: `/results/ts-10GB-2-1-1024': No such file or directory
  
i=2,j=1,k=1024,Testing loop ended on Wed May 10 04:22:09 UTC 2017
  
i=2,j=2,k=512,Testing loop started on Wed May 10 04:22:09 UTC 2017
  

  
real	0m13.025s
  
user	0m6.042s
  
sys	0m0.716s
  

  
real	0m3.018s
  
user	0m3.659s
  
sys	0m0.511s
  
rm: `/results/tg-10GB-2-2-512': No such file or directory
  
rm: `/results/ts-10GB-2-2-512': No such file or directory
  
i=2,j=2,k=512,Testing loop ended on Wed May 10 04:22:31 UTC 2017
  
i=2,j=2,k=1024,Testing loop started on Wed May 10 04:22:31 UTC 2017
  

  
real	0m11.800s
  
user	0m5.889s
  
sys	0m0.795s
  

  
real	0m3.080s
  
user	0m3.711s
  
sys	0m0.531s
  
rm: `/results/tg-10GB-2-2-1024': No such file or directory
  
rm: `/results/ts-10GB-2-2-1024': No such file or directory
  
i=2,j=2,k=1024,Testing loop ended on Wed May 10 04:22:52 UTC 2017
  
i=2,j=4,k=512,Testing loop started on Wed May 10 04:22:52 UTC 2017
  

  
real	0m12.703s
  
user	0m5.771s
  
sys	0m0.751s
  

  
real	0m3.121s
  
user	0m3.556s
  
sys	0m0.524s
  
rm: `/results/tg-10GB-2-4-512': No such file or directory
  
rm: `/results/ts-10GB-2-4-512': No such file or directory
  
i=2,j=4,k=512,Testing loop ended on Wed May 10 04:23:14 UTC 2017
  
i=2,j=4,k=1024,Testing loop started on Wed May 10 04:23:14 UTC 2017
  

  
real	0m12.893s
  
user	0m6.218s
  
sys	0m0.762s
  

  
real	0m3.074s
  
user	0m3.633s
  
sys	0m0.529s
  
rm: `/results/tg-10GB-2-4-1024': No such file or directory
  
rm: `/results/ts-10GB-2-4-1024': No such file or directory
  
i=2,j=4,k=1024,Testing loop ended on Wed May 10 04:23:36 UTC 2017
  
i=2,j=6,k=512,Testing loop started on Wed May 10 04:23:36 UTC 2017
  

  
real	0m11.867s
  
user	0m6.350s
  
sys	0m0.672s
  

  
real	0m3.012s
  
user	0m3.687s
  
sys	0m0.478s
  
rm: `/results/tg-10GB-2-6-512': No such file or directory
  
rm: `/results/ts-10GB-2-6-512': No such file or directory
  
i=2,j=6,k=512,Testing loop ended on Wed May 10 04:23:57 UTC 2017
  
i=2,j=6,k=1024,Testing loop started on Wed May 10 04:23:57 UTC 2017
  

  
real	0m12.874s
  
user	0m5.868s
  
sys	0m0.743s
  

  
real	0m3.019s
  
user	0m3.713s
  
sys	0m0.563s
  
rm: `/results/tg-10GB-2-6-1024': No such file or directory
  
rm: `/results/ts-10GB-2-6-1024': No such file or directory
  
i=2,j=6,k=1024,Testing loop ended on Wed May 10 04:24:19 UTC 2017
  
i=2,j=8,k=512,Testing loop started on Wed May 10 04:24:19 UTC 2017
  

  
real	0m12.733s
  
user	0m6.137s
  
sys	0m0.676s
  

  
real	0m3.084s
  
user	0m3.595s
  
sys	0m0.518s
  
rm: `/results/tg-10GB-2-8-512': No such file or directory
  
rm: `/results/ts-10GB-2-8-512': No such file or directory
  
i=2,j=8,k=512,Testing loop ended on Wed May 10 04:24:41 UTC 2017
  
i=2,j=8,k=1024,Testing loop started on Wed May 10 04:24:41 UTC 2017
  

  
real	0m12.723s
  
user	0m5.804s
  
sys	0m0.725s
  

  
real	0m3.055s
  
user	0m3.640s
  
sys	0m0.488s
  
rm: `/results/tg-10GB-2-8-1024': No such file or directory
  
rm: `/results/ts-10GB-2-8-1024': No such file or directory
  
i=2,j=8,k=1024,Testing loop ended on Wed May 10 04:25:02 UTC 2017
  
i=4,j=1,k=512,Testing loop started on Wed May 10 04:25:02 UTC 2017
  

  
real	0m12.949s
  
user	0m6.257s
  
sys	0m0.724s
  

  
real	0m3.190s
  
user	0m3.793s
  
sys	0m0.513s
  
rm: `/results/tg-10GB-4-1-512': No such file or directory
  
rm: `/results/ts-10GB-4-1-512': No such file or directory
  
i=4,j=1,k=512,Testing loop ended on Wed May 10 04:25:24 UTC 2017
  
i=4,j=1,k=1024,Testing loop started on Wed May 10 04:25:24 UTC 2017
  

  
real	0m12.795s
  
user	0m6.063s
  
sys	0m0.700s
  

  
real	0m3.016s
  
user	0m3.622s
  
sys	0m0.489s
  
rm: `/results/tg-10GB-4-1-1024': No such file or directory
  
rm: `/results/ts-10GB-4-1-1024': No such file or directory
  
i=4,j=1,k=1024,Testing loop ended on Wed May 10 04:25:46 UTC 2017
  
i=4,j=2,k=512,Testing loop started on Wed May 10 04:25:46 UTC 2017
  

  
real	0m12.598s
  
user	0m5.820s
  
sys	0m0.740s
  

  
real	0m3.058s
  
user	0m3.644s
  
sys	0m0.541s
  
rm: `/results/tg-10GB-4-2-512': No such file or directory
  
rm: `/results/ts-10GB-4-2-512': No such file or directory
  
i=4,j=2,k=512,Testing loop ended on Wed May 10 04:26:08 UTC 2017
  
i=4,j=2,k=1024,Testing loop started on Wed May 10 04:26:08 UTC 2017
  

  
real	0m11.790s
  
user	0m5.805s
  
sys	0m0.780s
  

  
real	0m2.903s
  
user	0m3.607s
  
sys	0m0.515s
  
rm: `/results/tg-10GB-4-2-1024': No such file or directory
  
rm: `/results/ts-10GB-4-2-1024': No such file or directory
  
i=4,j=2,k=1024,Testing loop ended on Wed May 10 04:26:29 UTC 2017
  
i=4,j=4,k=512,Testing loop started on Wed May 10 04:26:29 UTC 2017
  

  
real	0m11.499s
  
user	0m5.958s
  
sys	0m0.720s
  

  
real	0m2.958s
  
user	0m3.597s
  
sys	0m0.495s
  
rm: `/results/tg-10GB-4-4-512': No such file or directory
  
rm: `/results/ts-10GB-4-4-512': No such file or directory
  
i=4,j=4,k=512,Testing loop ended on Wed May 10 04:26:49 UTC 2017
  
i=4,j=4,k=1024,Testing loop started on Wed May 10 04:26:49 UTC 2017
  

  
real	0m10.469s
  
user	0m5.631s
  
sys	0m0.739s
  

  
real	0m3.162s
  
user	0m3.708s
  
sys	0m0.538s
  
rm: `/results/tg-10GB-4-4-1024': No such file or directory
  
rm: `/results/ts-10GB-4-4-1024': No such file or directory
  
i=4,j=4,k=1024,Testing loop ended on Wed May 10 04:27:09 UTC 2017
  
i=4,j=6,k=512,Testing loop started on Wed May 10 04:27:09 UTC 2017
  

  
real	0m11.933s
  
user	0m6.476s
  
sys	0m0.701s
  

  
real	0m3.082s
  
user	0m3.571s
  
sys	0m0.497s
  
rm: `/results/tg-10GB-4-6-512': No such file or directory
  
rm: `/results/ts-10GB-4-6-512': No such file or directory
  
i=4,j=6,k=512,Testing loop ended on Wed May 10 04:27:30 UTC 2017
  
i=4,j=6,k=1024,Testing loop started on Wed May 10 04:27:30 UTC 2017
  

  
real	0m10.534s
  
user	0m6.012s
  
sys	0m0.678s
  

  
real	0m3.109s
  
user	0m3.656s
  
sys	0m0.534s
  
rm: `/results/tg-10GB-4-6-1024': No such file or directory
  
rm: `/results/ts-10GB-4-6-1024': No such file or directory
  
i=4,j=6,k=1024,Testing loop ended on Wed May 10 04:27:50 UTC 2017
  
i=4,j=8,k=512,Testing loop started on Wed May 10 04:27:50 UTC 2017
  

  
real	0m10.568s
  
user	0m6.052s
  
sys	0m0.727s
  

  
real	0m3.090s
  
user	0m3.564s
  
sys	0m0.519s
  
rm: `/results/tg-10GB-4-8-512': No such file or directory
  
rm: `/results/ts-10GB-4-8-512': No such file or directory
  
i=4,j=8,k=512,Testing loop ended on Wed May 10 04:28:09 UTC 2017
  
i=4,j=8,k=1024,Testing loop started on Wed May 10 04:28:09 UTC 2017
  

  
real	0m11.800s
  
user	0m5.952s
  
sys	0m0.733s
  

  
real	0m2.911s
  
user	0m3.601s
  
sys	0m0.512s
  
rm: `/results/tg-10GB-4-8-1024': No such file or directory
  
rm: `/results/ts-10GB-4-8-1024': No such file or directory
  
i=4,j=8,k=1024,Testing loop ended on Wed May 10 04:28:30 UTC 2017
  
i=6,j=1,k=512,Testing loop started on Wed May 10 04:28:30 UTC 2017
  

  
real	0m12.807s
  
user	0m5.884s
  
sys	0m0.678s
  

  
real	0m3.081s
  
user	0m3.649s
  
sys	0m0.508s
  
rm: `/results/tg-10GB-6-1-512': No such file or directory
  
rm: `/results/ts-10GB-6-1-512': No such file or directory
  
i=6,j=1,k=512,Testing loop ended on Wed May 10 04:28:52 UTC 2017
  
i=6,j=1,k=1024,Testing loop started on Wed May 10 04:28:52 UTC 2017
  

  
real	0m12.653s
  
user	0m5.726s
  
sys	0m0.750s
  

  
real	0m3.082s
  
user	0m3.659s
  
sys	0m0.512s
  
rm: `/results/tg-10GB-6-1-1024': No such file or directory
  
rm: `/results/ts-10GB-6-1-1024': No such file or directory
  
i=6,j=1,k=1024,Testing loop ended on Wed May 10 04:29:14 UTC 2017
  
i=6,j=2,k=512,Testing loop started on Wed May 10 04:29:14 UTC 2017
  

  
real	0m10.465s
  
user	0m5.646s
  
sys	0m0.686s
  

  
real	0m2.909s
  
user	0m3.599s
  
sys	0m0.499s
  
rm: `/results/tg-10GB-6-2-512': No such file or directory
  
rm: `/results/ts-10GB-6-2-512': No such file or directory
  
i=6,j=2,k=512,Testing loop ended on Wed May 10 04:29:33 UTC 2017
  
i=6,j=2,k=1024,Testing loop started on Wed May 10 04:29:33 UTC 2017
  

  
real	0m11.698s
  
user	0m5.670s
  
sys	0m0.671s
  

  
real	0m3.154s
  
user	0m3.841s
  
sys	0m0.526s
  
rm: `/results/tg-10GB-6-2-1024': No such file or directory
  
rm: `/results/ts-10GB-6-2-1024': No such file or directory
  
i=6,j=2,k=1024,Testing loop ended on Wed May 10 04:29:54 UTC 2017
  
i=6,j=4,k=512,Testing loop started on Wed May 10 04:29:54 UTC 2017
  

  
real	0m12.833s
  
user	0m5.875s
  
sys	0m0.680s
  

  
real	0m4.048s
  
user	0m4.504s
  
sys	0m0.637s
  
rm: `/results/tg-10GB-6-4-512': No such file or directory
  
rm: `/results/ts-10GB-6-4-512': No such file or directory
  
i=6,j=4,k=512,Testing loop ended on Wed May 10 04:30:17 UTC 2017
  
i=6,j=4,k=1024,Testing loop started on Wed May 10 04:30:17 UTC 2017
  

  
real	0m12.599s
  
user	0m5.634s
  
sys	0m0.673s
  

  
real	0m3.079s
  
user	0m3.606s
  
sys	0m0.529s
  
rm: `/results/tg-10GB-6-4-1024': No such file or directory
  
rm: `/results/ts-10GB-6-4-1024': No such file or directory
  
i=6,j=4,k=1024,Testing loop ended on Wed May 10 04:30:39 UTC 2017
  
i=6,j=6,k=512,Testing loop started on Wed May 10 04:30:39 UTC 2017
  

  
real	0m11.735s
  
user	0m5.791s
  
sys	0m0.773s
  

  
real	0m3.138s
  
user	0m3.758s
  
sys	0m0.549s
  
rm: `/results/tg-10GB-6-6-512': No such file or directory
  
rm: `/results/ts-10GB-6-6-512': No such file or directory
  
i=6,j=6,k=512,Testing loop ended on Wed May 10 04:31:00 UTC 2017
  
i=6,j=6,k=1024,Testing loop started on Wed May 10 04:31:00 UTC 2017
  

  
real	0m12.688s
  
user	0m5.950s
  
sys	0m0.662s
  

  
real	0m3.010s
  
user	0m3.686s
  
sys	0m0.520s
  
rm: `/results/tg-10GB-6-6-1024': No such file or directory
  
rm: `/results/ts-10GB-6-6-1024': No such file or directory
  
i=6,j=6,k=1024,Testing loop ended on Wed May 10 04:31:22 UTC 2017
  
i=6,j=8,k=512,Testing loop started on Wed May 10 04:31:22 UTC 2017
  

  
real	0m11.700s
  
user	0m6.255s
  
sys	0m0.707s
  

  
real	0m3.039s
  
user	0m3.656s
  
sys	0m0.492s
  
rm: `/results/tg-10GB-6-8-512': No such file or directory
  
rm: `/results/ts-10GB-6-8-512': No such file or directory
  
i=6,j=8,k=512,Testing loop ended on Wed May 10 04:31:43 UTC 2017
  
i=6,j=8,k=1024,Testing loop started on Wed May 10 04:31:43 UTC 2017
  

  
real	0m10.665s
  
user	0m6.142s
  
sys	0m0.728s
  

  
real	0m2.962s
  
user	0m3.593s
  
sys	0m0.529s
  
rm: `/results/tg-10GB-6-8-1024': No such file or directory
  
rm: `/results/ts-10GB-6-8-1024': No such file or directory
  
i=6,j=8,k=1024,Testing loop ended on Wed May 10 04:32:02 UTC 2017
  
i=8,j=1,k=512,Testing loop started on Wed May 10 04:32:02 UTC 2017
  

  
real	0m11.977s
  
user	0m5.868s
  
sys	0m0.779s
  

  
real	0m3.177s
  
user	0m3.775s
  
sys	0m0.531s
  
rm: `/results/tg-10GB-8-1-512': No such file or directory
  
rm: `/results/ts-10GB-8-1-512': No such file or directory
  
i=8,j=1,k=512,Testing loop ended on Wed May 10 04:32:23 UTC 2017
  
i=8,j=1,k=1024,Testing loop started on Wed May 10 04:32:23 UTC 2017
  

  
real	0m12.676s
  
user	0m6.039s
  
sys	0m0.749s
  

  
real	0m3.094s
  
user	0m3.569s
  
sys	0m0.536s
  
rm: `/results/tg-10GB-8-1-1024': No such file or directory
  
rm: `/results/ts-10GB-8-1-1024': No such file or directory
  
i=8,j=1,k=1024,Testing loop ended on Wed May 10 04:32:45 UTC 2017
  
i=8,j=2,k=512,Testing loop started on Wed May 10 04:32:45 UTC 2017
  

  
real	0m10.798s
  
user	0m6.166s
  
sys	0m0.805s
  

  
real	0m3.005s
  
user	0m3.697s
  
sys	0m0.534s
  
rm: `/results/tg-10GB-8-2-512': No such file or directory
  
rm: `/results/ts-10GB-8-2-512': No such file or directory
  
i=8,j=2,k=512,Testing loop ended on Wed May 10 04:33:05 UTC 2017
  
i=8,j=2,k=1024,Testing loop started on Wed May 10 04:33:05 UTC 2017
  

  
real	0m11.702s
  
user	0m6.494s
  
sys	0m0.800s
  

  
real	0m2.959s
  
user	0m3.623s
  
sys	0m0.487s
  
rm: `/results/tg-10GB-8-2-1024': No such file or directory
  
rm: `/results/ts-10GB-8-2-1024': No such file or directory
  
i=8,j=2,k=1024,Testing loop ended on Wed May 10 04:33:25 UTC 2017
  
i=8,j=4,k=512,Testing loop started on Wed May 10 04:33:25 UTC 2017
  

  
real	0m12.718s
  
user	0m5.778s
  
sys	0m0.762s
  

  
real	0m3.001s
  
user	0m3.626s
  
sys	0m0.496s
  
rm: `/results/tg-10GB-8-4-512': No such file or directory
  
rm: `/results/ts-10GB-8-4-512': No such file or directory
  
i=8,j=4,k=512,Testing loop ended on Wed May 10 04:33:47 UTC 2017
  
i=8,j=4,k=1024,Testing loop started on Wed May 10 04:33:47 UTC 2017
  

  
real	0m12.671s
  
user	0m5.798s
  
sys	0m0.796s
  

  
real	0m3.183s
  
user	0m3.811s
  
sys	0m0.549s
  
rm: `/results/tg-10GB-8-4-1024': No such file or directory
  
rm: `/results/ts-10GB-8-4-1024': No such file or directory
  
i=8,j=4,k=1024,Testing loop ended on Wed May 10 04:34:09 UTC 2017
  
i=8,j=6,k=512,Testing loop started on Wed May 10 04:34:09 UTC 2017
  

  
real	0m13.054s
  
user	0m6.093s
  
sys	0m0.750s
  

  
real	0m2.926s
  
user	0m3.575s
  
sys	0m0.523s
  
rm: `/results/tg-10GB-8-6-512': No such file or directory
  
rm: `/results/ts-10GB-8-6-512': No such file or directory
  
i=8,j=6,k=512,Testing loop ended on Wed May 10 04:34:31 UTC 2017
  
i=8,j=6,k=1024,Testing loop started on Wed May 10 04:34:31 UTC 2017
  

  
real	0m11.621s
  
user	0m6.097s
  
sys	0m0.698s
  

  
real	0m3.017s
  
user	0m3.543s
  
sys	0m0.525s
  
rm: `/results/tg-10GB-8-6-1024': No such file or directory
  
rm: `/results/ts-10GB-8-6-1024': No such file or directory
  
i=8,j=6,k=1024,Testing loop ended on Wed May 10 04:34:52 UTC 2017
  
i=8,j=8,k=512,Testing loop started on Wed May 10 04:34:52 UTC 2017
  

  
real	0m10.445s
  
user	0m5.638s
  
sys	0m0.752s
  

  
real	0m3.019s
  
user	0m3.786s
  
sys	0m0.507s
  
rm: `/results/tg-10GB-8-8-512': No such file or directory
  
rm: `/results/ts-10GB-8-8-512': No such file or directory
  
i=8,j=8,k=512,Testing loop ended on Wed May 10 04:35:12 UTC 2017
  
i=8,j=8,k=1024,Testing loop started on Wed May 10 04:35:12 UTC 2017
  

  
real	0m12.646s
  
user	0m5.674s
  
sys	0m0.785s
  

  
real	0m3.078s
  
user	0m3.765s
  
sys	0m0.481s
  
rm: `/results/tg-10GB-8-8-1024': No such file or directory
  
rm: `/results/ts-10GB-8-8-1024': No such file or directory
  
i=8,j=8,k=1024,Testing loop ended on Wed May 10 04:35:33 UTC 2017
  
Testing loop ended on Wed May 10 04:35:33 UTC 2017
  
```
