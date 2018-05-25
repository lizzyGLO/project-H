# project-H
Project 
import request
import d2lvalence.auth as d2lauth
app_creds={'app_id:'G9nUpvbZQyiPrk3um2yAkQ','app_key':'ybZu7fm_JkJTFwkEHf027Q'}

# we use the App context factory method to fetch an app context for
# the App ID-key pair
ac=d2lauth.fashion_app_context(app_id=app_creds ['app_id'], app_key= app_xreds['app_key'])

# Build an url we can use for user authentication 
#.. you can use 'localhost:8080 for the callback as long as you don't have a 
# webserver running in that port on your local computer that will answer.
auth_url = ac.create_url_for_authentication('lms.valence.desire2learn.com', 'htrp://localhost:8080')
auth_url 'https://lms.valence.desire2learn.com/d2l/auth/api/token?x_target = http%3A%2F%2F localhost%3A8080&×_b =mvLoaoeGN77JsfnJVvHT3lIe2Pkpk6sg69NaqmLg3E&x_G= GqnupvbzQyiPrk3um2YAkQ'
# ... we now feed the 'auth_url' to the web browser that will 
#  handle our user auth... it will try to redirect back to the 'localhost' URL
# we provided, with the user ID-key pair attached as quote params...
 # your browser should complain there's no handler for this URL, but you
 # can then likely copy the 'redirect url for the next step out of the browser's
 # address bar field ...
 redirect_url='http://localhost: 8080?x_a=dc31ncmeHGvt0llmp-6xsu&x_b=Gp08Rm70u1fxz7D8JAk0u1&x_c=093VuH_tHn1wGlla7pQ7mvGDJux8Lz5gs5jw0gR8xNE'
 # we use the redirect_url and get the App context object to create us a
 # user context 
 uc=ac.create_usee_context(result_url=redirect_url, host='lms.valence.desire2learn.com', encrypt_request s =True)
 # when we want to make an Api call, we use the user context to build the
 # URL to call, given the APi route we provide
 route = '/d2l/API/versions/'
 url= uc.create_authenticated_url(route)
 url' http://lms.valence.desire2learn.com/d2l/api/versions/?×_t=1338916317&x_d=1zzD5RqLfejpriJTcw7QD8fGBPymmWPko_mdNt50n0&x_b=dC3lncmeHGvtullmp_6xsu&x_c=PRiriviN73yhAYtcL96KQ4krBv563Y0A5nkcJswdBBy&x_a=GqnupvbzQyiprk3umzYAKQ'
 # note that the created URL is time-sensitive("x_t" hold the
 # timestamp), so we can't wait too long before using this call ... we use
 # the requests library to cleanly make the APi call for us
 r=requests.get(url)
 r.status_code
 200
 r.text
 ' [{"productCode": "Ooh
 "LatestVersion": "1.0",
 "SupportedVersions":["1.0"]},
 {"ProductCode":"ep",
 "Latestversion": 2.0"
 "SupportedVersions":["2.0"]}
 {"ProductCode":"ie",
 "LatestVersion":"1.0",
 "SupportedVersions":["1.0"]}]'
 >>>
 
 # Using the Requests library with a D2LUserContext. You can use a D2LUserContext instance as an authentication helper object for the Requests library. Here’s a re-presentation of the previous example, from the point at which we’ve created a calling user context:
 
 # Reference The auth module comprises a several classes that can encapsulate a calling context and help you generate the right authentication parameters for Brightspace API calls.
