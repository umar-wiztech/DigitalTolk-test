Identified Issues
    1. Project documentation needs to be improved
        1. No class description available
        2. No description tag in function definition
        3. No author signature is present in documentaion


    2. Repository instance name "repository" in BookingController is not aligned with the standards. This should be "bookingRepository"

    3. In BookingController all methods uses response() method. However, response should be in json like
                response()
                -> json([$data], 'status' => 'true/false', 'message' => 'message', 'format' = 'json/xml')

    4. In BookingController there is "distanceFeed" method. Inside this method, there is a lot of messy code which should not be in controller. Controller should be clean as much as possible.

    5. In BookingContoller, except "resendSMSNotifications" method, there is not any exception handling in methods.

    6. In BookingRepository, there is Job repository modal injected in repository. However, it is not used as injected instance. There is no need to refer it with Job modal directory. Should be access through injected instance. On the whole, we should use any modal by inject it instead of accessing it with modal name.


    7. In repository store, there should be a single handler class that generate response.

    8. There should not be commented code in a project. 

    9. In BookingRepository, "sendPushNotificationToSpecificUsers" uses CURL for third party API hit. However, there is a laravel guzzle client that makes code more clean and simpler.

    10. There should be a separate Notification handler class that will manage all the notification payload prepare and notification sent event.

    11. I did not find any validation mechanism in the code.

    12. Lower readibility of code and linting issues

    
Possible Solutions:
    1. There should be proper documentation in the code for classes and functions.

    2. Repository instance name should be bookingRepository.

    3. Response method should be generic and diverse enough to support structure mentioned in point 3 above.

    4. Code should be clean especially when you are writing a controller. Move code and to service or repository layer.

    5. There should be standard exception handler mechanism

    6. Always use modals with injected instance. Never use modal with its name.

    7. Store should have generic class that handler and generate responses

    8. Remove all commented code from the project.

    9. Use more suitable libraries that can reduce code and make it easy to understand. Replace CURL eith Laravel Guzzle.

    10. Create generic notification handler that makes it easy to have clean code.

    11. Always use laravel form request for validation to reduce efforts and more clean code.

    12. Use a linter and prettier for code clean and increase readibility.

Remarks:
    I have identified few issues and refered possible fixes for that. However, due to shortage of time, I did not get
    a chance to refactor the existing code.
