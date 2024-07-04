# NIRSIT-Quest

This is a public repository for NIRSIT Quest support.

## Requirement

- MATLAB R2022a or later

## Installation

Copy the repository and register the top level path of the repository in matlab path.

```matlab
addpath(genpath('/your/repository/path'));
```

## Usage
### 1. Load file
#### 1.1. Load SNIRF file
```matlab
data = subjectClass('/your/snirf/data/path.sinrf')
```
```matlab
data = 
  subjectClass with properties:

         metadata: [1×1 struct]
             nirs: [1×1 rawDataClass]
           marker: [1×1 markerClass]
            block: [1×0 taskBlockClass]
        auxiliary: [1×1 auxDataClass]
          battery: [1×1 batteryClass]
    rejectionInfo: [21×1 table]
    formatVersion: "1.1"
      channelInfo: [21×5 table]
            probe: [1×1 struct]
```
#### 1.2. Load .prep file
```matlab
data = subjectClass('/your/processed/data/path.prep')
```
```matlab
data = 
  subjectClass with properties:

         metadata: [1×1 struct]
             nirs: [1×1 rawDataClass]
           marker: [1×1 markerClass]
            block: [1×0 taskBlockClass]
        auxiliary: [1×1 auxDataClass]
          battery: [1×1 batteryClass]
    rejectionInfo: [21×1 table]
    formatVersion: "1.1"
      channelInfo: [21×5 table]
            probe: [1×1 struct]
```
### 2. Save data
#### 2.1. Save data as SNIRF file
```matlab
saveas(data,'/your/snirf/data/path.snirf');
```
When saving data in SNIRF format, only raw intensity data will be saved.


#### 2.2. Save data as .prep file
```matlab
save(data,'/your/snirf/data/path.prep');
```
See the example code for more details.

## Supprot
For support, please contact us at [sales@obelab.com](<sales@obelab.com>).