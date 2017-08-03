# assignment_designing_nosql_data_models
I'll have one data model hold the SQL please


Andrew and Ed

BASIC)

{
  id: int, serialize
  username: str, user chooses, 
  pw: str, encrypted
  settings: {
    time_format: index of format
    color_scheme: index of a scheme
    remember: bool
  }
  profile: {
    birthday: timestamp
    gender: str or one of array
    phone #: string, #s and (-, ., +,   ()) only
    description: text, varying
    location: {
      city: str 
      state: str
      country: str
      gps: str, calculated not entered
      time_zone: signed int (GMT offset)
      }
    visibility: (booleans) {
      birthday:
      gender:
      phone #:
      location:
         }
  }







}