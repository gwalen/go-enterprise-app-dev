#### Configure app using file or environment variables

Go has multiple packages that allow reading configuration from file or environment variables.

I have experimented with [Viper](https://github.com/spf13/viper) which a great tool.

It allows to read config from :
* JSON, TOML, YAML, HCL, envfile and Java properties config files
* environment variables
* remote config systems (etcd or Consul)

It also allows watching live changes in that files during application lifetime.

For full set of capabilities please read the Github web page.

#### Conclusion

There are tools that are easy to use and powerful to cope with this task.
