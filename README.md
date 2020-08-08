# cfn-modules: AWS Lambda event source: Kinesis data stream

Kinesis data stream event source for AWS Lambda function.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/lambda-event-source-kinesis-data-stream
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  EventSource:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        LambdaModule: !GetAtt 'Function.Outputs.StackName' # required
        DataStreamModule: !GetAtt 'DataStream.Outputs.StackName' # required
        BatchSize: '10' # optional
        StartingPosition: 'LATEST' # optional
      TemplateURL: './node_modules/@cfn-modules/lambda-event-source-kinesis-data-stream/module.yml'
```

## Examples

none

## Related modules

* [kinesis-data-stream](https://github.com/cfn-modules/kinesis-data-stream)
* [lambda-function](https://github.com/cfn-modules/lambda-function)

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>LambdaModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/lambda-function">lambda-function module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>DataStreamModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/kinesis-data-stream module">kinesis-data-stream module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>BatchSize</td>
      <td>The largest number of messages that Lambda retrieves from your stream at once.</td>
      <td>10</td>
      <td>no</td>
      <td>[1-10000]</td>
    </tr>
    <tr>
      <td>StartingPosition</td>
      <td>The position in the stream where Lambda starts reading</td>
      <td>LATEST</td>
      <td>no</td>
      <td>[LATEST, TRIM_HORIZON]</td>
    </tr>
  </tbody>
</table>
