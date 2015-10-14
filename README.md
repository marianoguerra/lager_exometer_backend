lager exometer backend
======================

A lager backend that sends metrics of logs per level to exometer.

To avoid depending on specific versions of lager and exometer this lib
doesn't list them as dependencies, you app should have lager and exometer
as dependencies.

Configure
---------

on rebar add this to your deps:

    {lager_exometer_backend, ".*", {git, "https://github.com/marianoguerra/lager_exometer_backend", {branch, "master"}}}

on rebar3:

    {lager_exometer_backend, {git, "https://github.com/marianoguerra/lager_exometer_backend", {branch, "master"}}}

The lager section of your config should have a lager_exometer_backend
handler like this:

     {lager, [
       {handlers, [
         {lager_exometer_backend, [{level, info}]},
         ... other handlers here ...
       ]}
     ]}

your metrics will be in:

    [lager_exometer, log, Level]
