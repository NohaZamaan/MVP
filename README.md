<img src="https://github.com/NohaZamaan/Project_T5/blob/main/Images/%D8%A7%D9%94%D9%83%D8%A7%D8%AF%D9%8A%D9%85%D9%8A%D8%A9-%D8%B3%D8%AF%D8%A7%D9%8A%D8%A7.png" width="150" height="150"> Project Name: Microsoft Malware Prediction 
---

<b>By:</b>  Noha Abdulwahab Zamaan

***

## CONTENTS :
 * Introduction
 * Libraries
 * Data Preprocessing 
 * Methodology 
   - Dealing with Features
   - Modeling
 * Results and Conclusion 
 * Resources

---

### Introduction:

Industries of malware and hacking are very powerful and growth sharply. It works to harm millions of victims and companies. These industries have great funding from a variety of organizations and people to meet their purposes. However, large global companies like Microsoft work hard to defense their customer from any attack.
Microsoft provides its dataset ‘ https://www.kaggle.com/c/microsoft-malware-prediction’ that includes many features about its consumer’s machine devices that collected by by Microsoft's endpoint protection solution and Windows Defender.<p> 
<B> Microsoft </B> challenges the data scientist to apply various machine learning models to predict malware before occurring.
  
---
   
### Data Description

| Feature_Name | Description |
| ----          | ------------------- |
|MachineIdentifier | Individual machine ID|
|ProductName | Defender state information e.g. win8defender|
|EngineVersion |Defender state information e.g. 1.1.12603.0|
|AppVersion | Defender state information e.g. 4.9.10586.0|
|AvSigVersion | Defender state information e.g. 1.217.1014.0|
|IsBeta | Defender state information e.g. false|
|DefaultBrowsersIdentifier | ID for the machine's default browser|
|AVProductStatesIdentifier |ID for the specific configuration of a user's antivirus software|
|HasTpm | True if machine has tpm|
|CountryIdentifier | ID for the country the machine is located in|
|CityIdentifier | ID for the city the machine is located in|
|OrganizationIdentifier | ID for the organization the machine belongs in, organization ID is mapped to both specific companies and broad industries|
|GeoNameIdentifier | ID for the geographic region a machine is located in|
|LocaleEnglishNameIdentifier | English name of Locale ID of the current user|
|Platform | Calculates platform name (of OS related properties and processor property)|
|Processor | This is the process architecture of the installed operating system|
|OsVer | Version of the current operating system|
|OsBuild | Build of the current operating system|
|OsSuite | Product suite mask for the current operating system.|
|OsPlatformSubRelease | Returns the OS Platform sub-release (Windows Vista, Windows 7, Windows 8, TH1, TH2)|
|OsBuildLab | Build lab that generated the current OS. Example: 9600.17630.amd64fre.winblue_r7.150109-2022|
|SkuEdition | The goal of this feature is to use the Product Type defined in the MSDN to map to a 'SKU-Edition' name that is useful in population reporting. The valid Product Type are defined in %sdxroot%\data\windowseditions.xml. This API has been used since Vista and Server 2008, so there are many Product Types that do not apply to Windows 10. The 'SKU-Edition' is a string value that is in one of three classes of results. The design must hand each class.|
|IsProtected | This is a calculated field derived from the Spynet Report's AV Products field. Returns: a. TRUE if there is at least one active and up-to-date antivirus product running on this machine. b. FALSE if there is no active AV product on this machine, or if the AV is active, but is not receiving the latest updates. c. null if there are no Anti Virus Products in the report. Returns: Whether a machine is protected.|
|AutoSampleOptIn -|This is the SubmitSamplesConsent value passed in from the service, available on CAMP 9+|
|PuaMode | Pua Enabled mode from the service|
|SMode | This field is set to true when the device is known to be in 'S Mode', as in, Windows 10 S mode, where only Microsoft Store apps can be installed|
|SmartScreen | This is the SmartScreen enabled string value from registry. This is obtained by checking in order, |HKLM\SOFTWARE\Policies\Microsoft\Windows\System\SmartScreenEnabled and HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\SmartScreenEnabled. If the value |exists but is blank, the value "ExistsNotSet" is sent in telemetry.|
|Firewall | This attribute is true (1) for Windows 8.1 and above if windows firewall is enabled, as reported by the service.|
|UacLuaenable | This attribute reports whether or not the "administrator in Admin Approval Mode" user type is disabled or enabled in UAC. The value reported is |obtained by reading the regkey HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\EnableLUA.|
|Census_MDC2FormFactor | A grouping based on a combination of Device Census level hardware characteristics. The logic used to define Form Factor is rooted in business and industry standards and aligns with how people think about their device. (Examples: Smartphone, Small Tablet, All in One, Convertible...)|
|Census_DeviceFamily | AKA DeviceClass. Indicates the type of device that an edition of the OS is intended for. Example values: Windows.Desktop, Windows.Mobile, and iOS.Phone|
|Census_ProcessorCoreCount | Number of logical cores in the processor|
|Census_ProcessorClass | A classification of processors into high/medium/low. Initially used for Pricing Level SKU. No longer maintained and updated|
|Census_PrimaryDiskTotalCapacity | Amount of disk space on primary disk of the machine in MB|
|Census_PrimaryDiskTypeName | Friendly name of Primary Disk Type - HDD or SSD|
|Census_SystemVolumeTotalCapacity | The size of the partition that the System volume is installed on in MB|
|Census_HasOpticalDiskDrive | True indicates that the machine has an optical disk drive (CD/DVD)|
|Census_TotalPhysicalRAM | Retrieves the physical RAM in MB|
|Census_ChassisTypeName | Retrieves a numeric representation of what type of chassis the machine has. A value of 0 means xx|
|Census_InternalPrimaryDiagonalDisplaySizeInInches | Retrieves the physical diagonal length in inches of the primary display|
|Census_InternalPrimaryDisplayResolutionHorizontal | Retrieves the number of pixels in the horizontal direction of the internal display.|
|Census_InternalPrimaryDisplayResolutionVertical | Retrieves the number of pixels in the vertical direction of the internal display|
|Census_PowerPlatformRoleName | Indicates the OEM preferred power management profile. This value helps identify the basic form factor of the device|
|Census_OSVersion | Numeric OS version Example - 10.0.10130.0|
|Census_OSArchitecture | Architecture on which the OS is based. Derived from OSVersionFull. Example - amd64|
|Census_OSBranch | Branch of the OS extracted from the OsVersionFull. Example - OsBranch = fbl_partner_eeap where OsVersion = 6.4.9813.0.amd64fre.fbl_partner_eeap.140810-0005|
|Census_OSBuildNumber | OS Build number extracted from the OsVersionFull. Example - OsBuildNumber = 10512 or 10240|
|Census_OSBuildRevision | OS Build revision extracted from the OsVersionFull. Example - OsBuildRevision = 1000 or 16458|
|Census_OSEdition | Edition of the current OS. Sourced from HKLM\Software\Microsoft\Windows NT\CurrentVersion@EditionID in registry. Example: Enterprise|
|Census_OSSkuName | OS edition friendly name (currently Windows only)|
|Census_OSInstallTypeName | Friendly description of what install was used on the machine i.e. clean|
|Census_OSWUAutoUpdateOptionsName | Friendly name of the WindowsUpdate auto-update settings on the machine.|
|Census_IsPortableOperatingSystem | Indicates whether OS is booted up and running via Windows-To-Go on a USB stick.|
|Census_GenuineStateName | Friendly name of OSGenuineStateID. 0 = Genuine|
|Census_ActivationChannel | Retail license key or Volume license key for a machine.|
|Census_IsFlightsDisabled | Indicates if the machine is participating in flighting.|
|Census_FlightRing | The ring that the device user would like to receive flights for. This might be different from the ring of the OS which is currently installed if the user changes the ring after getting a flight from a different ring.|
|Census_IsSecureBootEnabled | Indicates if Secure Boot mode is enabled.|
|Census_IsVirtualDevice | Identifies a Virtual Machine (machine learning model)|
|Census_IsTouchEnabled | Is this a touch device ?|
|Census_IsPenCapable | Is the device capable of pen input ?|
|Census_IsAlwaysOnAlwaysConnectedCapable | Retreives information about whether the battery enables the device to be AlwaysOnAlwaysConnected .|
|Wdft_IsGamer | Indicates whether the device is a gamer device or not based on its hardware combination.|
  
### Libraries:
  
- <B> For reading file </B> --> Ex: pandas 
- <B> For Visualization </B> --> Ex:seaborn
- <B> For Modeling </B> --> Ex: RandomForestClassifier
- <B> For Metrics </B> --> Ex: accuracy_score
- <B> For scaling </B> --> Ex: StandardScaler
- <B> For validation </B> --> Ex: cross_val_score

---
  
### Data Preprocessing 
  
The dataset was very big , it contains 8921482 rows so,I decided to cut it in  10000 rows.<p>
the dataset divided into a training set (90%) and a testing set (10%).<p>
There were 10 columns that have unavalible data or null so, I drop them all. <p>
Other features that had some missing values, presented to see the type of them. <p>
All missing values were in numorical columns, then Visualized to see thier distribution <p>
![distribution](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.29.05%20PM.png) 
Most columns have unnormal distribution so, using 'median' to fill the missing value is the best. <p>
Using 'get_dummy' function to convert all categorical columns <p>
Then apply heatmap to approve no missing value in the data and print the new shape of the data   <p>
![missing](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.29.48%20PM.png) <p>  

---

### Methodology <p>
#### - Dealing with Features <p>
After using dummy, there are 12347 columns. It is unpossible to use all these features for modeling 
<p> So, I tried to use different techniques
- Select the best 10 features by:
   1)feature_importances_ from ExtraTreesClassifier: <p>
      
   ![feature_importances_](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.30.34%20PM.png) <p>
      
   2)SelectKBest from chi2:<p>
      
   ![SelectKBest](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.30.51%20PM.png) <p>
      
   3)feature_importances_ from RandomForestRegressor: <p>
      
   ![rf_feature_importances_](https://github.com/NohaZamaan/Project_T5/blob/main/Images/Screen%20Shot%201443-04-10%20at%2010.31.02%20PM.png) <p>
      
- Using Principal Component Analysis (PCA) with n_components=6 <p>
   
   
#### - Modeling

   - Logistic Regression Model with Pipline, Scaling, GridSearch <p>
   
| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| ExtraTreesClassifier  | 0.548 | 0.537 |
| SelectKBest |0.591 |0.596|
|Random Forest Feature Importances |0.549 | 0.562| 

<p> I select the best two score to apply the next model on them <p>
   
   - KNeighborsClassifier Model with Pipline, Scaling, GridSearch <p>
   
| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| SelectKBest |0.587  |0.592|
|Random Forest Feature Importances |0.505 | 0.499|
   
   - Random Forest Classifier Model with Pipline, Scaling, GridSearch <p>  
 
| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| SelectKBest |0.59  |0.596|
|Random Forest Feature Importances |0.585 | 0.585|
| PCA  | - | 0.54 |
      
   - Neural_Network Model <p>
      

| Method_Name | Train_Score | Test_Score |
| :---:   | :-: | :-: |
| SelectKBest | - |0.581|

      
### Results and Conclusion 
      
- Random Forest was the best model performance with Scaling and GridSearch methods :+1: . However, it consumed the longest time in execution. <p>  
- The Feature_selection with ‘SelectKBest()’ function can be the best method when applying models on it, so, may approve it on huge features. <p>
- Still, the score isn’t good even though trying a variety  of parameters, GridSearch, and scaling the data. <p>
- Maybe it needs other features that have more correlation with the target, or there are external conditions that affect  the target. <p>
- This result leads us to agree that, some problems are still hard to predict their solution for them even though they have data about them. :shipit: <p>



### Resources:
      
[1] https://medium.com/@erikgreenj/k-neighbors-classifier-with-gridsearchcv-basics-3c445ddeb657 <p>

[2] https://towardsdatascience.com/random-forest-ca80e56224c1 <p>

[3] https://medium.com/@amrianto.saragih/4-methods-to-boost-the-accuracy-of-a-neural-network-model-bb694e650a69 <p>

[4] https://towardsdatascience.com/pca-using-python-scikit-learn-e653f8989e60 <p>

[5] https://towardsdatascience.com/machine-learning-step-by-step-6fbde95c455a <p>




