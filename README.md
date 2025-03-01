# rn-goal-graph

# RNGoals![ScreenRecording2025-03-01at8 21 00PM-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/ce39adf4-b355-49db-9ee9-fc9bee187593)


## Installation

Install the package using npm or yarn:

```sh
npm install rn-goal-graph

or

yarn add rn-goal-graph

# Usage
import React, { FunctionComponent, useState } from "react";
import { Text, View } from "react-native";
import { CustomGoalGraph } from "rn-goal-graph";
import { moderateScale } from "./src/constant/responsiveStyle";
import colors from "./src/constant/colors";

interface CustomGoalsProps {}

const CustomGoals: FunctionComponent<CustomGoalsProps> = () => {
  const [selectedTimePeriod, setSelectedTimePeriod] = useState("Week");

  const handleTimePeriodChange = (period: string) => {
    setSelectedTimePeriod(period);
    console.log("Selected Time Period:", period);
  };

  const sampleData = [
    { progress: 75 },
    { progress: 50 },
    { progress: 90 },
    { progress: 30 },
    { progress: 60 },
    { progress: 40 },
    { progress: 80 },
  ];

  const sampleData1 = [
    { progress: 12 },
    { progress: 7 },
    { progress: 9 },
    { progress: 80 },
    { progress: 54 },
    { progress: 38 },
    { progress: 23 },
  ];
  return (
    <View
      style={{
        flex: 1,
        backgroundColor: colors.themeColor,
        justifyContent: "center",
        alignItems: "center",
      }}
    >
      <View style={{ marginHorizontal: moderateScale(10) }}>
        <CustomGoalGraph
          goalName="Steps"
          selectableList={["week", "month"]}
          data_={selectedTimePeriod == "week" ? sampleData : sampleData1}
          dates={
            selectedTimePeriod == "week"
              ? ["24-02-2025", "", "", "", "", "", "02-03-2025"]
              : ["24-02-2025", "", "", "", "", "", "23-03-2025"]
          }
          setSelectedTimePeriod={handleTimePeriodChange}
          isiSAnimationRequired={true}
          mainContainerBG={'#yourchoiceofcolor'}
        />
      </View>
    </View>
  );
};

export default CustomGoals;

```
