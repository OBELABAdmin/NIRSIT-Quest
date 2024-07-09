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

### 3. Modifying Markers
```matlab
data = subjectClass('/your/processed/data/path.prep');

data.marker.marker(data.marker.marker~=0)'
ans =
  1×31 uint32 row vector
   7777   8888   1111   2222   1000   1001   1111   2222   2000   2001   1111   2222   3000   3001   1111   2222   4000   4001   1111   2222   5000   5001   1111   2222   6000   6001   1111   2222   7000   7001   9999

data.marker.marker(data.marker.marker == 7777) = 1234;

data.marker.marker(data.marker.marker~=0)'
ans =
  1×31 uint32 row vector
   1234   8888   1111   2222   1000   1001   1111   2222   2000   2001   1111   2222   3000   3001   1111   2222   4000   4001   1111   2222   5000   5001   1111   2222   6000   6001   1111   2222   7000   7001   9999

save(data,'/your/snirf/data/path.prep');
```
See the example code for more details.

## Supprot
For support, please contact us at [sales@obelab.com](<sales@obelab.com>).