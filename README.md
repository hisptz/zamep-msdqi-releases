# zamep-msdqi-release

## Introduction

This repository for public release of all app version of **ZAMEP MSDQI APP** as well custom checklist conigurations to support the custom look and feel of paper based tools

For release of app, can be accessed either [google playstore](https://play.google.com/store/apps/details?id=com.hipstz.dhis2.dhis2touch.zamep.eds) or on this [releases page](https://github.com/hisptz/zamep-msdqi-releases/releases) for manual donwload and installations.

## Custom forms configurations

Custom configuration has been down with concept of tables and division of checklist into combination of checklist's section and sub sections. In which section or subsection can have tables's rows as row of inputs fields or labels as per checklist paper based design.

The two major overall design based on JSON format and pattern for checklist's custom desing, one for **QIP** which is a bit trick as it has some custom logics and custom input fields and other which is common for rest of checklist (**ANC, IPD, OPD, Logistics, Microscopy, mRDT and SME**).

The design can editied with any JSON editor or using [Online JSON Editor](https://jsoneditoronline.org/) for easy editing these custom designs.

### Summary of fields for forms configuration

| Keys               | Descriptions                                                                                                                                                                                                                                                                                                                                           | value type                            |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------- |
| Sections           | Attributes for define section                                                                                                                                                                                                                                                                                                                          | Array list of section                 |
| programStage       | Id referrence for program stage for checklist                                                                                                                                                                                                                                                                                                          | string                                |
| isQipForm          | Field to indicate if the form a QIP or not                                                                                                                                                                                                                                                                                                             | Boolean (true, false)                 |
| minimumScore       | Value used for QIP generation, the minimum value indicator to be available for QIP geneartion                                                                                                                                                                                                                                                          | Number                                |
| qipDataSources     | List of program ids for each checklist to be included on QIP                                                                                                                                                                                                                                                                                           | List/Array of string                  |
| customDataElements | List of custom data element to be used on QIP entry forms. Its array of list object with **id,valueType and options**. But options includes list of objects with **code, name**                                                                                                                                                                        |                                       |
| indicatoLegends    | List of color and maximum value for custom color for program indicators in a specific checklist. it used to define color and maximum value for the specific legends. I contains list of object with **color and maximum**. For instance `[{"color":"#FF0000","maximum":"500"},{"color":"#FFFF00","maximum":"75"},{"color":"#088000","maximum":"100"}]` | List of object with **color,maximum** |

### Summary of fields for section/sub sections configuration

| Keys        | Descriptions                                                             | Value type                        |
| ----------- | ------------------------------------------------------------------------ | --------------------------------- |
| title       | Title for section or subsection                                          | String                            |
| instruction | Hints or instruction for section or subsection                           | String                            |
| subSections | List of subsection if any for a give section based on paper tools design | List/Array of type section        |
| inputRows   | List of rows to define columns for each table design                     | List/Array of list of columns row |

### Summary of fields for columns's row configuration

| Keys            | Descriptions                                                                                                     | Value type                 |
| --------------- | ---------------------------------------------------------------------------------------------------------------- | -------------------------- |
| id              | Id of data element or program indicator to be used as inout field                                                | String                     |
| label           | Label to displayed on colums based on design                                                                     | String                     |
| backgroundColor | Background color for cell in table view of an input field or label. It's hex color format for instance `#1B9688` | String                     |
| htmlLabel       | Label with formatted html contents                                                                               | String                     |
| hints           | Hints or instructions on specifuc columns                                                                        | String                     |
| flex            | Number of columns merged into one cell                                                                           | Number                     |
| isBolded        | Property used to indicate whether to bold specified label or not                                                 | String                     |
| suffixLabel     | Label to be attached at end of input field. It mostly used together with program indicators                      | String                     |
| subInputs       | List of rows to be attached on a given column's cell.                                                            | List/Array of column's row |
