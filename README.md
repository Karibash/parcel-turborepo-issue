# parcel-turborepo-issue

This minimally reproduces the problems that occur when Parcel and Turborepo are combined.

## Steps to reproduce

1. Clone this repository
2. Run `pnpm install` in the root of the repository
3. Run `pnpm run build:parcel` in the root of the repository
4. Sometimes the build passes successfully, other times it exits without response.

## Expected behavior

The build should always pass successfully.

## Actual behavior

The build sometimes exits without response.  
The following output is from that case:

```shell
 Tasks:    0 successful, 10 total
Cached:    0 cached, 10 total
  Time:    2.011s
```

## Additional context

This problem is not reproduced when the number of packages is small.  
In my environment, it is reproduced when the number of packages is more than 5.  
Also, the larger the number of packages, the more unstable it becomes.

And this problem seems to occur only with Parcel.  
It did not reproduce when using other bundlers such as tsup or esbuild.  
You can run `pnpm run build:tsup` in this repository to see if it works with tsup.
