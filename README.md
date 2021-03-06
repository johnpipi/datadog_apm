# DatadogApm

This gem is notified of basic performance metrics for a Rails application, and sends the measurements to DataDog.

## Installation

Install the [Datadog Agent](https://app.datadoghq.com/account/settings#agent) on your application server. This gem only
works on servers which have the Datadog Agent installed.

Add this line to your application's Gemfile:

    gem 'datadog_apm'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install datadog_apm

## Usage

By default, performance metrics are only reported to Datadog from production environments which have the
[Datadog agent](https://app.datadoghq.com/account/settings#agent) installed.

To enable Datadog reporting in non-production environments, add the following to an initializer:

    DatadogApm.configure do |config|
      config.environments = ['staging', 'production']
    end

To add additional tags, add the following to the configuration:

    config.tags = ['role:myapp', 'host:myapp-1', 'region:east']

Override the default metric name with the following configuration:

    config.metric = :apm

## Contributing

1. Fork it ( https://github.com/johnpipi/datadog_apm/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
