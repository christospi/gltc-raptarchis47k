### GLTC - Raptarchis Data Parser

Developed to generate a prosperous dataset, ideal for the text-classification tasks.  
Original documents can be found at: http://www.e-themis.gov.gr/

Main parsing script: *file_reader.py*

Some notes:

Better run on interpreter mode. Example:

    # For re-importing modules i.e. imp.reload(ut)
    import imp
    
    import file_reader as fr
    import utils as ut
    import data_boost as db
    
    # Parse and sort tree hierarchy of Raptarchis Data
    rn = fr.parse_file()
    
    # Fetch year for every law
    ut.fetch_year(rn)
    
    # Fetch possible ID for every law
    ut.fetch_law_id(rn)
    
    # Generate the appropriate legislation URI
    ut.generate_leg_uri(rn)
    
    # Dump everything to JSON files
    ut.dump_to_files(rn)
    
    # Find laws that are mentioned more than once in corpus
    ut.tuned_expose_duplicates()
    
    # initial method that produces duplicates_final.txt
    # ut.expose_duplicates()
    
    # Enhance data with content from Legislation
    db.legislation_boost()
    
    # Remove all duplicate entries
    ut.remove_duplicates()
    
    # ----- EXTRA - STATISTICS etc. -----
    # Write law headers in files (more info at function)
    ut.show_headers(rn, True)
