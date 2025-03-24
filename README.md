# Hi there 👋

GoSuit is a collection of tools for Go developers. It is designed to make things like error handling, configuration, and others simpler and more concise. You can see examples of using the library in the <a href="https://github.com/nikitaSstepanov/go-template">go-template</a>.

## Tools

Here is the list of tools provided:

- <a href="https://github.com/gosuit/e">Error handling</a>
- <a href="https://github.com/gosuit/sl">Logging</a>
- <a href="https://github.com/gosuit/lec">Logging Error Context</a>
- <a href="https://github.com/gosuit/confy">Configuration reader</a>
- <a href="https://github.com/gosuit/httper">Working with HTTP</a>
- <a href="https://github.com/gosuit/pg">PostgreSQL client</a>
- <a href="https://github.com/gosuit/rs">Redis client</a>
- <a href="https://github.com/gosuit/mongo">MongoDB client</a>
- <a href="https://github.com/gosuit/minio">MinIO client</a>
- <a href="https://github.com/gosuit/migrate">Migrations runner</a>
- <a href="https://github.com/gosuit/mail">Simple mailling</a>
- <a href="https://github.com/gosuit/gins">Lec syntactic sugar for Gin</a>
- <a href="https://github.com/gosuit/utils">Usefull utils</a>

## Configuration

All configuration types in the GoSuit have YAML, JSON and ENV struct tags. We recommend use <a href="https://github.com/gosuit/confy">Confy</a> or <a href="https://github.com/ilyakaznacheev/cleanenv">CleanEnv</a> to read configs.

### Exampe

```golang
package main

import (
  "github.com/gosuit/confy"
  "github.com/gosuit/pg"
  "github.com/gosuit/rs"
)

type Config struct {
  Postgres pg.Config `yaml:"postgres"`
  Redis    rs.Config `yaml:"redis"`
}

func main() {
  path := "config.yaml"
  var cfg Config

  err := confy.Get(path, &cfg)
  if err != nil {
    // Handle error...
  }

  // Use config...
}
```
