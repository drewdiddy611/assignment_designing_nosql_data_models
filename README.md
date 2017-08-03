# assignment_designing_nosql_data_models
I'll have one data model hold the SQL please


Andrew and Ed

BASIC)
[Users Blueprint]
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
[Table Index Blueprint]
// Indexes for available tables
{
	"9:00": [5, 7, 12] // Tables 5, 7, and 12 are available.
	"10:00": [3, 7, 12, 10, 15] // Tables 5, 7, and 12 are available.
	"11:00": [3, 4, 5] // Tables 5, 7, and 12 are available.
}

[Server Index Blueprint]
// Indexes for wait-staff serving corresponding table for that time slot.
{
	"9:00": [5, 7, 12] // Server 5, 7, and 12 are available.
	"10:00": [3, 7, 12, 10, 15] // Server 5, 7, and 12 are available.
	"11:00": [3, 4, 5] // Server 5, 7, and 12 are available.
}

[Tables Blueprint]
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

INTERMEDIATE-2)
[Users Blueprint]
{
	id: int, serialize
  username: str, user chooses,
  pw: str, encrypted
	semesters: {
	  season_year: {
			class_id: {
				instructor: str,
				teachers_assistant: str,
				overall_grade: str or number?,
				exams: {
					exam_id: {
						grade: str or number?
					}
				}
			}
		}
	}
}


Advanced 1)

<!-- // depts
dept: {
  product1: {
    product_id: varchar
    current_price: int
    price_history: {
      month_year: int
    }
    description: text, unlimited
  }
} -->

Products: {
  product_id:
  dept:
  price:
  quantity_in_stock_now:
  sales_history: {
    month_year: {
      price:
      cost: 
      units_sold:
      revenue:
    }
  }
}

Transactions: {
  transaction_id: {
    product_id: {
      {PRODUCT} //sales history?
      units_sold:      
      revenue:
    }
  }
}

//index table for depts' product ids
Dept_Products_index_table: {
  dept1: [product_id_A, product_id_B, product_id_C]
  dept2: [product_id_x, product_id_Y, product_id_Z]
}

Sales_Histories: {
  product_id: {
    month_year: {
      price:
      cost: 
      units_sold:
      revenue:
    }
  }
}




}




