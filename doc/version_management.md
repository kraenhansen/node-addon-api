# VersionManagement

The `Napi::VersionManagement` class contains methods that allow information
to be retrieved about the version of Node-API and Node.js. In some cases it is
important to make decisions based on different versions of the system.

## Methods

### GetNapiVersion

Retrieves the highest Node-API version supported by Node.js runtime.

```cpp
static uint32_t Napi::VersionManagement::GetNapiVersion(Napi::BasicEnv env);
```

- `[in] env`: The environment in which the API is invoked under.

Returns the highest Node-API version supported by Node.js runtime.

### GetNodeVersion

Retrieves information about Node.js version present on the system. All the
information is stored in the `napi_node_version` structure that is defined as
shown below:

```cpp
typedef struct {
  uint32_t major;
  uint32_t minor;
  uint32_t patch;
  const char* release;
} napi_node_version;
````

```cpp
static const napi_node_version* Napi::VersionManagement::GetNodeVersion(Napi::BasicEnv env);
```

- `[in] env`: The environment in which the API is invoked under.

Returns the structure a pointer to the structure `napi_node_version` populated by
the version information of Node.js runtime.
