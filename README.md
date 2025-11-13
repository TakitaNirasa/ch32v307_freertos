# ch32v307_freertos

#### First install wlink (cargo needed)

```bash
git clone https://github.com/ch32-rs/wlink
cd wlink
cargo build -Znext-lockfile-bump
sudo cp target/debug/wlink /usr/share
sudo ln -s /usr/share/wlink /usr/bin/wlink
wlink --version
```

#### Second - you need riscv-none-elf toolchain (https://xpack-dev-tools.github.io/riscv-none-elf-gcc-xpack/docs/install/)

```bash
xpm install @xpack-dev-tools/riscv-none-elf-gcc@latest --global --verbose
echo 'export PATH=$HOME/.local/xPacks/@xpack-dev-tools/riscv-none-elf-gcc/15.2.0-1.1/.content/bin:$PATH' >> ~/.bashrc
```

#### Third - install cmake, ninja

```bash
sudo apt install cmake ninja-build
ninja --version
cmake --version
```
At this moment you get all you need to build firmware


### Build firmware
#### Preparing
```bash
git clone https://github.com/TakitaNirasa/ch32v307_freertos.git
cd ch32v307_freertos
mkdir build
cd build
```
#### Building
```
cmake -GNinja ..
ninja
```

#### Flashing
```
sudo wlink flash ch32v307-freertos.elf
```
