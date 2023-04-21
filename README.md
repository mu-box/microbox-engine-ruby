# Ruby

This is a Ruby engine used to launch Ruby apps on [Microbox](http://microbox.cloud). It installs all binaries to run a Ruby app.

# Usage
To use the Ruby engine, specify `ruby` as your engine in your [boxfile.yml](http://docs.microbox.cloud/app-config/boxfile/).

```yaml
run.config:
  engine: ruby
```

## Build Process
When then engine builds and prepares the code, it runs the following:

- `bundle install`
- `bundle clean`

## Configuration Options
This engine exposes configuration options through the [boxfile.yml](http://docs.microbox.cloud/app-config/boxfile/), a yaml config file used to provision and configure your app's infrastructure when using Microbox.

#### Overview of Basic Boxfile Configuration Options
```yaml
run.config:
  engine: ruby
  engine.config:
    runtime: ruby-2.2
    postgresql_client_version: "9.6"
```

---

#### runtime
Specifies which Ruby runtime and version to use. The following runtimes are available:

- ruby-1.9
- ruby-2.0
- ruby-2.1
- ruby-2.2
- ruby-2.3 *(default)*
- ruby-2.4
- ruby-2.5
- jruby-1.6
- jruby-1.7
- jruby-9.0

```yaml
run.config:
  engine.config:
    runtime: 'ruby-2.3'
```

---

#### postgresql_client_version
If the 'pg' gem is detected the engine will install the postgresql client. You can specify the version to install using `postgresql_client_version` in your `boxfile.yml`.

**NOTE**: The engine will try to detect the correct version first.

- 9.3
- 9.4
- 9.5
- 9.6
- 10

```yaml
run.config:
  engine.config:
    postgresql_client_version: "9.6"
```

---

## Ruby on Microbox
For more information about using Ruby on Microbox, view the [Ruby guides](http://guides.microbox.cloud/ruby/).

## Help & Support
This is an engine provided by [Microbox](http://microbox.cloud). If you are running into an issue with the engine, feel free to [create a new issue on this project](https://github.com/mu-box/microbox-engine-ruby/issues/new).
