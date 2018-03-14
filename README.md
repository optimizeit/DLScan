# DLScan
Install from pod 

platform :ios, '9.0'


use_frameworks!

target 'TestApp' do
  pod 'DrivingLicenceScan', :podspec => 'https://raw.githubusercontent.com/optimizeit/DLScan/master/DrivingLicenceScan.podspec'
end




import DrivingLicenceScan

Add DrivingLicenseScanDelegate

Write code in the following manner 
	let objIDScan = IDScanModule()
        objIDScan.delegate = self
        let btn1 = UIButton()
        btn1.setTitle("First", for: .normal)
        btn1.setTitleColor(UIColor.blue, for: .normal)
        btn1.tag = 0
        btn1.backgroundColor = UIColor.red

        let btn2 = UIButton()
        btn2.setTitle("First", for: .normal)
        btn2.setTitleColor(UIColor.blue, for: .normal)
        btn2.tag = 1
        btn2.backgroundColor = UIColor.red

        let backGroundColor = UIColor.gray

        var dicTemp = [String : Any]()
        dicTemp = ["frontBtn" : btn1,"backBtn" : btn2,"backGroundColor" : backGroundColor]
        
        
        objIDScan.showIDScanVC(dataDic: dicTemp)

Use the following delegate to get the call back 

func bringIDScanVC(IDScanView: UIView)
    {
        IDScanView.frame = self.view.frame
        self.view.addSubview(IDScanView)
    }
    
    func callBackFromIDScan(actionName: String, imageArray: [UIImage], drivingLicenceModel : DrivingLicenceModel)
    {
        
    }



Optional for skip and continue 

func exitButtonPress()



