
import UIKit




class ViewController: UIViewController {
    
    let contextView: UIView = {
        var view = UIView(frame: CGRect(x: 20, y: 270, width: 356, height: 323))
        view.backgroundColor = .systemGreen
        view.layer.cornerRadius = 25
        return view
    }()
   
    
     var textField : UITextField {
         let textfield = UITextField()
         
             textfield.frame = CGRect(x: 100, y: 380, width: 200, height: 50)
             textfield.font = UIFont.systemFont(ofSize: 22, weight: .black)
             textfield.placeholder = .some("Email")
         textfield.textAlignment = .center
         textfield.borderStyle = UITextField.BorderStyle.roundedRect
             textfield.leftViewMode = .always
        
         
             return textfield
         
     }
    var textField2 : UITextField {
        let textfield2 = UITextField()
        
            textfield2.frame = CGRect(x: 100, y: 450, width: 200, height: 50)
            textfield2.font = UIFont.systemFont(ofSize: 22, weight: .black)
            textfield2.placeholder = .some("Pasword")
            textfield2.textAlignment = .center
        textfield2.borderStyle = UITextField.BorderStyle.roundedRect
            textfield2.leftViewMode = .always
       
        
            return textfield2
        
    }
    
    
    lazy var textLabel :  UILabel = {
        let textLabel = UILabel()
        textLabel.text = "Регистрация"
        textLabel.numberOfLines = 0
        textLabel.frame = CGRect(x: 130 , y: 220, width: 200, height: 200)
        textLabel.lineBreakMode = .byCharWrapping
        textLabel.font = UIFont.systemFont(ofSize: 22, weight: .black)
        textLabel.textColor = UIColor(red: 149/256, green: 125/256, blue: 120/256, alpha: 1)
        
        
        return textLabel
    }()
    

    lazy var someButton : UIButton = {
            
        let button = UIButton()
        button.setTitle("Войти", for: .normal)
        button.setTitle("Удачно", for: .highlighted)
        button.setTitleColor(.black, for: .normal)
        button.titleLabel?.font = UIFont.systemFont(ofSize: 20, weight: .light)
        button.frame.size = CGSize(width: view.frame.width - 40 , height: 120)
        button.frame.origin = CGPoint(x: 20, y: 470)
        button.layer.cornerRadius = 25
        button.restorationIdentifier = "btn1"
        button.addTarget(self, action: #selector(btnTouch(sender: )), for: .touchUpInside)
        return button
    
    } ()
        override func viewDidLoad() {
            super.viewDidLoad()
            view.addSubview(contextView)
            view.addSubview(textLabel)
            view.addSubview(someButton)
            view.addSubview(textField)
            view.addSubview(textField2)
    }
    
    @objc func btnTouch (sender : UIButton){
        
        if sender.restorationIdentifier == "btn1" {
            print("работаем")
        
        }

        print(sender.restorationIdentifier as Any)
    }
    
}

