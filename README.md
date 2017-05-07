# quiz_gt
//
//  ViewController.swift
//  TrFa
//
//  Created by G S THIND on 5/7/17.
//  Copyright © 2017 G S THIND. All rights reserved.
//

import UIKit
struct Question {
    var Question : String!
    var Answers : [String]!
    var Answer : Int!
}



class ViewController: UIViewController {

    @IBOutlet var Buttons: [UIButton]!
    @IBOutlet var QLabel: UILabel!
    
    var Questions = [Question]()
    
    var QNumber = Int()
    
    var AnswerNumber = Int()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        
        Questions = [Question(Question: "Largest Aircraft", Answers: ["Dreamliner","Airbus","A380","Concorde"], Answer: 2),
        Question(Question: "Best City", Answers: ["London","Sydney","Ludhiana","Dallas"], Answer: 3),
        Question(Question: "Wow Car", Answers: ["Bugatti","Ferrari","Camaro","Jeep"], Answer: 0),
        Question(Question: "Biggest Ocean", Answers: ["Indian","Pacific","Atlantic","Caspian"], Answer: 1),]
        
        PickQuestion()
        

    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }

    func PickQuestion(){
        
        if Questions.count > 0 {
            QNumber = 0
            QLabel.text = Questions[QNumber].Question
            
            AnswerNumber = Questions[QNumber].Answer
            
            for i in 0..<Buttons.count{
                Buttons[i].setTitle(Questions[QNumber].Answers[i], for: UIControlState.normal)
            }
            
            Questions.remove(at: QNumber)
            
        }
        else{
            
            NSLog("Done!")
        }
    }


    @IBAction func Btn1(_ sender: Any) {
        if AnswerNumber == 0{
            
            PickQuestion()
        }
        else{
            NSLog("Wrong!")
        }
        
    }
    
    @IBAction func Btn2(_ sender: Any) {
        if AnswerNumber == 1{
            
            PickQuestion()
        }
        else{
            NSLog("Wrong!")
        }
    }
    
    @IBAction func Btn3(_ sender: Any) {
        if AnswerNumber == 2{
            
            PickQuestion()
        }
        else{
            NSLog("Wrong!")
        }
    }
    
    @IBAction func Btn4(_ sender: Any) {
        if AnswerNumber == 3{
            
            PickQuestion()
        }
        else{
            NSLog("Wrong!")
        }
    }
    
}
