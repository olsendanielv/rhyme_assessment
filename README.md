# Rhyme Assessment

## Assumptions Made
* During data loading, if a value is not in the expected datatype, we coerce it to be NaN/Null.
* Data Cleaning
    * For both names and emails:
        * Leading/trailing whitespace can be ignored/removed
        * Casing does not matter
        * Invisible characters can be removed
    * For emails:
        * Some known emails can be fixed (see fix_domain() function for more)
        * We can remove periods in the local part of specific email addresses
            * Gmail and Protonmail are both known to ignore periods while the others do not. 
    * For names:
        * First word in `name` is first_name
        * Last word in `name` is last_name
        * Any word in the middle is considered a middle name
        * If we only get 1 name, we will use it for the first_name
* Joining and displaying the data
    * We are doing a left join (events to users) that way we can flag events that do not link to users 
    * However, we only write the inner join results to the output CSV file