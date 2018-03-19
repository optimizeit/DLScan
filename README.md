# DLScan
Install from pod 

platform :ios, '9.0'


use_frameworks!

target 'TestApp' do
  pod 'DrivingLicenceScan', :podspec => 'https://raw.githubusercontent.com/optimizeit/DLScan/master/DrivingLicenceScan.podspec'
end




import DrivingLicenceScan

Add DrivingLicenseScanDelegate

Write code in the following manner in any action

	let obj = ScanLicensebackVC()
 	obj.delegate = self
        obj.bringDrivingicenseBarcodeScanVC()

Use the following delegate to get the call back 

    func showDrivingicenseBarcodeScanVC(scanLicensebackVC : ScanLicensebackVC)
    {
        self.present(scanLicensebackVC, animated: true, completion: nil)
    }
    
    func drivingLicenseScanData(mappingDictionary : NSMutableDictionary)
    {
        // Get all the data which come from the barcode scan.
    }



