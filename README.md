#### pkmasrabbitmq
#####cp4 Clustering and high
federation:loose coupling, WAN friendly, scalability
```
rabbitmq-plugins enable rabbitmq_federation rabbitmq_federation_management
```
define a upstream using
```
rabbitmqctl set_parameter federation-upstream test '{"uri":"amqp://localhost","expires":72000}'
```
set policy
```
rabbitmqctl set_policy --apply-to exchanges ke "^amq\." '{"federation-upstream-set":"all"}'
```

#####cp5 Plugins
```
rabbitmq-plugins list -veEm
```
use 3rd plugins
```
git clone git://github.com/jbrisbin/random-exchange.git
cd random-exchange
make exchange
cp dist/*.ez /usr/lib/rabbitmq/lib/rabbitmq_server-3.6.2/plugins
```
