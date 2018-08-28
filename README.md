# bedrock
The simple, easy to use python interface for Minecraft Bedrock worlds you've been waiting for.

## Quickstart
```python
import bedrock

with bedrock.World(path-to-save) as world:
  block = bedrock.Block("minecraft:stone") # Name must include `minecraft:`
  world.setBlock(0, 0, 0, block)
  block = bedrock.Block("minecraft:stone", 2) # Data value
  world.setBlock(0, 1, 0, block)
  if world.getBlock(0, 2, 0).name = "minecraft:stone":
    print("More stone!")
# Autosave on close.

print("Done!")
```

## Usage
### World
`World(path)`

`world.getBlock(x, y, z)`

`world.setBlock(x, y, z, block)`

### Block
`Block(name, dv=0, nbt=None)`

`block.name`

`block.dv`

`block.nbt`

### CommandBlock
`CommandBlock(command="", hoverText="", blockType="I", direction="u", conditional=False, needsRedstone=False)`

`blockType` can be one of `I`, `C`, `R`. `direction` can be one of `u`, `d`, `+x`, `-x`, `+z`, `-z`.

Otherwise identical to `Block`.

## Binaries
bedrock requires a leveldb-mcpe binary from https://github.com/Mojang/leveldb-mcpe, or one of its forks if that is easier for you to build. On windows, this means a `.dll` named LevelDB-MCPE-<architecture>.dll, where <architecture> is either 32 or 64. **The architecture should match your python install, not your windows install**. On linux this means `libleveldb.so`, which still must match your python install architecture. Two DLLs and a 64 bit .so are provided, but there is no gurantee as to the updatedness (or security) of any of them. If you get an error that mentions ctypes and importing, you probably need to build your own leveldb binary. Be sure to **use Mojang's leveldb-mcpe and not the google leveldb when building**.
