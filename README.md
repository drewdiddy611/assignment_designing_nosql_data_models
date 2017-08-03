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

INTERMEDIATE-1)

// Indexes for available tables
{
	"9:00": [5, 7, 12] // Tables 5, 7, and 12 are available.
	"10:00": [3, 7, 12, 10, 15] // Tables 5, 7, and 12 are available.
	"11:00": [3, 4, 5] // Tables 5, 7, and 12 are available.
}

// Indexes for wait-staff serving corresponding table for that time slot.
{
	"9:00": [5, 7, 12] // Server 5, 7, and 12 are available.
	"10:00": [3, 7, 12, 10, 15] // Server 5, 7, and 12 are available.
	"11:00": [3, 4, 5] // Server 5, 7, and 12 are available.
}

// Data table
{
	tables: [
		{
			id: int, serialize,
			available_seats: int // Make sure reservation guest_count not greater than this
			time_slots: { // child slots null if not reserved.
			  "9:00": {
					name: str (reservation name),
					guest_count: int,
					telephone: string, #s and (-, ., +,   ()) only
				},
				"10:00": null
				"11:00": null
			}
		}
	]
}
