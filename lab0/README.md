# A Kernel Seedling
This kernel module shows the current number of running processes. The proc_count.c file contains the source code to create a read-only 'count' file in the /proc/ folder. When the file is read, the proc_count function is called, which counts and outputs the number of running processes. The count file is then discarded from /proc/ when 'proc_remove()' is called. 

The makefile is responsible for building the kernel module. The test_lab0.py file is a python tester file.  

## Building
```shell
make
```

## Running
```shell
sudo insmod proc_count.ko
cat /proc/count 
```

157

## Cleaning Up
```shell
sudo rmmod proc_count.ko 
make clean
```

## Testing
```python
python -m unittest
```

...

----------------------------------------------------------------------

Ran 3 tests in 2.006s

OK



Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```
Linux 5.14.8-arch1-1 #1 SMP PREEMPT Sun, 26 Sep 2021 19:36:15 +0000

