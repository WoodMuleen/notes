# Leo_RPC Users Reference

## Leo_RPC Function List

* [`start/0`](#start0)
* [`async_call/4`](#async_call4)
* [`call/4,5,6`](#call456)
* [`multicall/4,5`](#multicall45)
* [`nb_yield/1,2`](#nb_yield12)
* [`cast/4`](#cast4)
* [`ping/1`](#ping1)
* [`status/0`](#status0)
* [`node/0`](#node0)
* [`nodes/0`](#nodes0)
* [`port/0`](#port0)

## Leo_RPC Function Reference

### `start/0`

#### Usage

```Erlang
leo_rpc:start() -> ok | {error, any()}.
```

#### Explanation

Launch leo-rpc

#### Types

- - -

### `async_call/4`

#### Usage

```Erlang
async_call(Node, Mod, Method, Args) -> pid().
```

#### Explanation
Implements call streams with promises, a type of RPC which does not suspend the caller until the result is finished.
Instead, a key is returned which can be used at a later stage to collect the value.
The key can be viewed as a promise to deliver the answer.

#### Types

* `Node` = `atom()`
* `Mod` = `module()`
* `Method` = `atom()`
* `Args` = `[any()]`

- - -

### `call/4,5,6`

#### Usage

```Erlang
leo_rpc:call(Node, Mod, Method, Args) -> any() | {badrpc, any()}
leo_rpc:call(Node, Mod, Method, Args, Timeout) -> any() | {badrpc, any()}
leo_rpc:call(From, Node, Mod, Method, Args, Timeout) -> any() | {badrpc, any()}
```

#### Explanation

Evaluates apply(Module, Function, Args) on the `Node` node and returns the result or `{badrpc, Reason}` if the call fails.

#### Types

* `Node` = `atom()`
* `Mod` = `module()`
* `Method` = `atom()`
* `Args` = `[any()]`
* `Timeout` = `pos_integer()`
* `From` = `pid()`

- - -

### `multicall/4,5`

#### Usage

```Erlang
leo_rpc:multicall(Nodes, Mod, Method, Args) -> any() | {badrpc, any()}.
leo_rpc:multicall(Nodes, Mod, Method, Args, Timeout) -> any() | {badrpc, any()}.
```

#### Explanation

A multicall is an RPC which is sent concurrently from one client to multiple servers.
This is useful for collecting some information from a set of nodes.

#### Types

* `Node` = `atom()`
* `Mod` = `module()`
* `Method` = `atom()`
* `Args` = `[any()]`
* `Timeout` = `pos_integer()`

- - -

### `nb_yield/1,2`

#### Usage

```Erlang
leo_rpc:nb_yield(Key) -> {value, any()} | timeout.
leo_rpc:nb_yield(Key, Timeout) -> {value, any()} | timeout.
```

#### Explanation

This is able to call non-blocking.
It returns the tuple {value, Val} when the computation has finished, or timeout when Timeout milliseconds has elapsed.

#### Types

* `Key` = `pid()`
* `Timeout` = `pos_integer()`

- - -

### `cast/4`

#### Usage

```Erlang
leo_rpc:cast(Node, Module, Method, Args) -> true.
```

#### Explanation

No response is delivered and the calling process is not suspended until the evaluation is complete, as is the case with call/4,5.

#### Types

* `Node` = `atom()`
* `Mod` = `module()`
* `Method` = `atom()`
* `Args` = `[any()]`

- - -

### `ping/1`

#### Usage

```Erlang
leo_rpc:ping(Node) -> pong|pang.
```

#### Explanation

Tries to set up a connection to Node.
Returns pang if it fails, or pong if it is successful.

#### Types

* `Node` = `atom()`

- - -

### `status/0`

#### Usage

```Erlang
leo_rpc:status() -> {ok, list(#rpc_info{})} | {error, any()}.
```

#### Explanation

Retrieve status of active connections.

#### Types

- - -

#### Usage

### `node/0`

```Erlang
leo_rpc:node() -> 'nonode@nohost' | atom().
```

#### Explanation

Returns the name of the local node. If the node is not alive, nonode@nohost is returned instead.

#### Types

- - -

#### Usage

### `nodes/0`

```Erlang
leo_rpc:nodes() -> [atom()]
```

#### Explanation

Returns a list of all connected nodes in the system, excluding the local node.

#### Types

- - -

### `port/0`

#### Usage

```Erlang
leo_rpc:port() -> integer().
```

#### Explanation

Returns the port number of the local node.

#### Types

- - -
