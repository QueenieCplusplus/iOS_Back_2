# iOS_Back_2
Camera Feature: to touch screen to call the camera, and save image in photo lib

1. add K/V to ask for users auhthorization to camera usage and usage of image saving.

         Privacy - Camera Usage Description
         Privacy - Photo Lib Add Usage Description
         
         
  ![](https://raw.githubusercontent.com/QueenieCplusplus/iOS_Back_2/main/info_property_list_2.png)
     
2. code in ControllerView.


        //  ViewController.swift
        //  KatesCamera
        //
        //  Created by KatesAndroid on 2021/1/27.
        //

        import UIKit

        class ViewController: UIViewController, UINavigationControllerDelegate, UIImagePickerControllerDelegate {

            override func viewDidLoad() {
                super.viewDidLoad()
                // Do any additional setup after loading the view.
            }

            override func touchesEnded(_ touches: Set<UITouch>, with event: UIEvent?) {

                let imgP = UIImagePickerController()
                imgP.sourceType = .camera
                imgP.delegate = self
                show(imgP, sender: self)
            }

            func imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [UIImagePickerController.InfoKey : Any]) {
                let img = info[UIImagePickerController.InfoKey.originalImage] as! UIImage

                UIImageWriteToSavedPhotosAlbum(img, nil, nil, nil)
                dismiss(animated: true, completion: nil)
            }


        }
        
    ref: https://stackoverflow.com/questions/41717115/how-to-make-uiimagepickercontroller-for-camera-and-photo-library-at-the-same-tim
        
3. run iPhone Simulator.

  ![](https://raw.githubusercontent.com/QueenieCplusplus/iOS_Back_2/main/exception.png)
  
4. Reason for Exception Error occured.

  ![](https://raw.githubusercontent.com/QueenieCplusplus/iOS_Back_2/main/reason.png)


