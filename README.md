lager exometer backend
======================

A lager backend that sends metrics of logs per level to exometer.

To avoid depending on specific versions of lager and exometer this lib
doesn't list them as dependencies, you app should have lager and exometer
as dependencies.

Configure
---------

The lager section of your config should have a lager_exometer_backend
handler like this::

     {lager, [
       {handlers, [
         {lager_metrics_backend, [{level, info}]},
         ... other handlers here ...
       ]}
     ]}
