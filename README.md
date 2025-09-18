# Pandas3

1 Problem 1 :Calculate Special Bonus ( https://leetcode.com/problems/calculate-special-bonus/)
Solution:

import pandas as pd

def calculate_special_bonus(employees: pd.DataFrame) -> pd.DataFrame:
    employees['bonus'] = employees['salary'].where(
       (~employees['name'].str.startswith('M')) & (employees['employee_id'] % 2 == 1), 0
   )
    return employees[['employee_id', 'bonus']].sort_values('employee_id')

2 Problem 2 : Fix Names in a Table	(	https://leetcode.com/problems/fix-names-in-a-table/ )
Solution:
import pandas as pd
def fix_names(users: pd.DataFrame) -> pd.DataFrame:
    users["name"] = users["name"].apply(lambda x: x[0].upper() + x[1:].lower())
    return users.sort_values(by="user_id")


3 Problem 3 : Patients with a Condition ( https://leetcode.com/problems/patients-with-a-condition/)
Solution:
import pandas as pd
def find_patients(patients: pd.DataFrame) -> pd.DataFrame:
    df = patients[(patients["conditions"].str.startswith("DIAB1")) |(patients["conditions"].str.contains(" DIAB1"))]
    return df




