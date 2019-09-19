# MarkdownEX01B

# EX02B

## Step One

PET-INFO-OWNER-INFO (PetName, PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Date, Charge)

Functional Dependencies: PetName  (PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName,    OwnerPhone, OwnerEmail)
   OwnerEmail  (OwnerLastName, OwnerFirstName, OwnerPhone)
   OwnerPhone  (OwnerLastName, OwnerFirstName, OwnerEmail)
   (PetName, Data)  (Service, Charge)


PET-INFO-OWNER-INFO Candidate Keys: (PetName, Date)
Not every determinant is a candidate key.
PetName, OwnerEmail and OwnerPhone are not candidate keys.

## Step Two

Break in to two relations which are OWNER-INFO and PET-INFO
OWNER-INFO (OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)
PET-INFO (PetName, PetType, PetBreed, PetDOB, Service, Date, Charge)





### OWNER-INFO
Functional Dependencies: OwnerPhone  (OwnerLastName, OwnerFirstName, OwnerEmail)
    OwnerEmail  (OwnerLastName, OwnerFirstName, OwnerPhone)

Candidate Keys
Every determinant is a candidate key so OwnerEmail and OwnerPhone are candidate keys

OwnerEmail = Primary Key 
OWNER-INFO (OwnerEmail, OwnerLastName, OwnerFirstName, OwnerPhone)
PET-INFO (PetName, PetType, PetBreed, PetDOB, OwnerEmail, Service, Date, Charge)

### PET-INFO
Functional Dependencies: PetName  (PetType, PetBreed, PetDOB, OwnerPhone)
  (PetName, Date)  (Service, Charge)

### PET-INFO 
Candidate Key:
(PetName, Date) – PetName is not a determinant so it is not a candidate key

## Step Three

PET-INFO separated into PET and INFO
OWNER-INFO (OwnerEmail, OwnerLastName, OwnerFirstName, OwnerPhone)
PET (PetName, PetType, PetBreed, PetDOB, OwnerPhone)
INFO (PetName, Date, Service, Charge)


### PET
Functional Dependencies: PetName  (PetType, PetBreed, PetDOB, OwnerPhone)

### PET 
Candidate Key: PetName
Every Determinant is a Candidate Key
(PetName, Date)  (Service, Charge)

### SERVICE 
Functional Dependencies: (PetName, Date)  (Service, Charge)

### SERVICE 
Candidate Keys: (PetName, Date)
Every Determinant is a Candidate Key

Finished Normalized Relations: OWNER-INFO (OwnerEmail, OwnerLastName, OwnerFirstName, OwnerPhone)
			             PET (PetName, PetType, PetBreed, PetDOB, OwnerEmail)
			             INFO (PetName, Date, Service, Charge)
