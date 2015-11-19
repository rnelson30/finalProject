# finalProject - PolyClubs - Matt Orgill, Ivonne Guzman, Ryan Nelson, Elvis Tran
/* APP Decscription:  PolyClubs is an app that allows students to easily stay up to date with their favorite clubs.
Presidents of the clubs will be given admin accounts so that they can upload all the events for their club.  Students
can then see these events on the app and never miss an event.  Of course, students will have to make accounts and find the clubs they want in order to store their favorite ones.  Once they have their favorites, it is very easy for them to see any new events for their clubs.  In addition, the main page will have a list of upcoming events throughout the school in case the students are looking for something new to try out.
So far, our app sends and receives data from Parse which allows new events to be created.  Basically, the admin user can hit the "add new event" button and fill out the information for their event.  Then once they hit submit, their information is sent to Parse.  Lastly, when any user goes to the club's page, they can see the event listed.  We are also working on hard coding all of the different clubs and implementing a log in page so that users can save their favorite clubs.
*/


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
