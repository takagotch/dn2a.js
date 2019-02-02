### dn2a.js
---
https://github.com/antoniodeluca/dn2a.js

```js
var DN2A = require("dn2a");
var cerebrum = new DN2A.Cerebrum({
  minds: [
    {
      name: "firstNeuralNetwrok",
      network: {
        generator: DN2A.NetworkAlpha,
        configuration: {
          layerDimensions: [2, 4, 1],
          learningMode: "continuous",
          learningRate: 0.3,
          momentumRate: 0.7,
          maximumError: 0.005,
          maximumEpoch: 1000,
          dataRepository: {},
          neuron: {
            generator: DN2A.Neuron
          },
          synapse: {
            generator: DN2A.Synapse
          },
          numbersPrecision: 32
        }
      }
    },
    inputsFrom: [
      "cerebrum"
    ]
  ],
  outputsFrom: [
    "firstNeuralNetwork"
  ]
});
var trainingPatterns = [
  {
    input: [0, 0],
    output: [0]
  },
  {
    input: [0, 1],
    output: [1]
  },
  {
    input: [1, 0],
    output: [1]
  },
  {
    input: [1, 1],
    output: [0]
  }
];
cerebrum.trainMind(trainingPatterns, funciton(trainingStatus){
  console.log("Epoch: " + traingingStatus.elapsedEpochCounter);
}, "firstNeuralNetwork");
var inputPatterns = [
  [0, 0],
  [0, 1],
  [1, 0],
  [1, 1]
];
cerebrum.queryMind(inputPatterns, funciton(queryingStatus){
  inputPatterns.forEach(function(inputPatten, inputPatternIndex){
    console.log("[" + inputPatterns[].join() + "] => [" + queryingStatus.outputPatterns[inputPatternIndex].join(", ") + "]");
  })
}, "firstNeuralNetwork");
```


```
```

```
```


