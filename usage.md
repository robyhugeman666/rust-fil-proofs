### 自定义rust编译



#### 1，下载rust-filecoin-proofs-api包到本地，注意版本

```shell
cd /root
git clone https://github.com/filecoin-project/rust-filecoin-proofs-api.git
git checkout v5.4.0
cd rust-filecoin-proofs-api
vim Cargo.toml
```
修改如下内容为

>filecoin-proofs-v1 = { package = "filecoin-proofs", path = "/root/rust-fil-proofs/filecoin-proofs" }

#### 2，下载rust-fil-proofs包到本地
```
git clone git@github.com:robyhugeman666/rust-fil-proofs.git

```

#### 3，修改lotus内部包关系
```
cd lotus/extern/filecoin-ffi/rust
vim Cargo.toml
```

```
[dependencies.filecoin-proofs-api]
package = "filecoin-proofs-api"
##改成
path = "/root/rust-filecoin-proofs-api"
##
```

#### 4，编译--->替换代码，重启miner
