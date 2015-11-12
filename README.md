# finalProject
//hi

Parse.setApplicationId("ubRUTFi6Lm0eVdfPTdw07lRB79pI12RBwizS3fZa",
  clientKey: "SuE5ov6kNhDdXllOoTO2StqnBypA2H9VJp7chGGT")
  
  //Beggining of the code. Uploading Event title, Location and description to Parse -Ivonne
  
class ViewController: UIViewController {
    
    @IBOutlet weak var Event: UITextField!
    
    @IBOutlet weak var Time: UITextField!
    
    @IBOutlet weak var Location: UITextField!
    

    @IBOutlet weak var Description: UITextView!
    
    @IBAction func Submit(sender: AnyObject) {
        let event = PFObject(className: "NewEvent")
        event["Event"] = Event.text!
        event["Time"] = Time.text!
        event["Location"] = Location.text!
        event["Description"] = Description.text!
        
        event.saveInBackground()
        Event.text = ""
        Time.text = ""
        Location.text = ""
        Description.text = ""
    }
