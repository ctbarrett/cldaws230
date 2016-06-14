# Custom cloudWatch alarm

The following command was used to create a custom metric & alarm

```bash
$ aws cloudwatch put-metric-alarm --alarm-name cb99-cw-tstAlarm \
> --alarm-description 'Test for custom alarm' --namespace 'craigbarrett.xyz/TestAPI' \
> --metric-name 'TestCondition' --statistic Sum --period 60 --threshold 2 --unit Count \
> --evaluation-periods 1 --comparison-operator GreaterThanThreshold \
> --dimensions 'Name=API,Value=ForceFail' \
> --alarm-actions "arn:aws:sns:us-east-1:907677783442:NotifyMe"
```

The following script was intended to generate random data over threshold to trigger custom alarm (didn't work)

```bash
#!/usr/bin/bash
let count=1
let max=45
let interval=2
while [[ $count -le $max ]]
do
  echo "Pushing data point $count..."
  aws cloudwatch put-metric-data --namespace 'craigbarrett.xyz/TestAPI' \
    --metric-name TestCondition --dimensions 'Name=API,Value=ForceFail' --unit Count \
    --value $(($RANDOM%12 + 3))
  sleep $interval
  ((count+=1))
done
```
