# How to run test suite for XRV1

- install this framework with "pip install --editable ."
- clone https://github.com/spacemonkeydelivers/MRV
- build xrv1 with "cmake -DCPU_RESET_ADDRESS=2000 -DBUILD_PYTHON_LIBRARY=ON -DCPU_RAM_SIZE_BITS=22 <..>/MRV/sw"
- copy xrv1 from <..>/MRV/sw/dut/ to build directory
- build Sail model as shown in https://hackmd.io/@ivywang2015/rvvm-riscof?utm_source=preview-mode&utm_medium=rec
- run "riscof setup --dutname=xrv1"
- edit config.ini and add "PATH=<xrv1 build dir>" to xrv1 dut and path to Sail as shown in step 5
- run "riscof run --config=config.ini --suite=riscv-arch-test/riscv-test-suite/ --env=riscv-arch-test/riscv-test-suite/env"
