# Hibernate

## Creating a table and inserting values to the database (Create)

### Step 1: Create a class with getters , settres and toString()
![Screenshot 2025-05-22 062106](https://github.com/user-attachments/assets/1b61ec84-8a52-4cbc-990d-43d24060ea72)
- @Entity represents table
- @Id represents primary key
### Step 2: Create `hibernate.cfg.xml` page
![Screenshot 2025-05-21 072426](https://github.com/user-attachments/assets/b5df5023-ab08-493a-a9dc-934a28f19124)
### Step 3: Create Connection page
![Screenshot 2025-05-21 072414](https://github.com/user-attachments/assets/f52de8be-80da-472d-856e-481f1c8d052b)

## Fetching data(Objects) from the database (Read)

- using primary key
![Screenshot 2025-05-22 063112](https://github.com/user-attachments/assets/9e4a7c68-2b06-462f-ae19-adda9b200feb)

## Update data in the database (Update)

### Note: Whenever we are performing any changes in the database we should **Transaction** and at the end we have to **commit** it.

- If the data on which we wanna perform update is not present then it will insert the new data that we are trying to inset.
![Screenshot 2025-05-22 064501](https://github.com/user-attachments/assets/f1772b59-7991-4382-8d57-60076c5f3c3c)

## Dalete data in the database (Delete)

![Screenshot 2025-05-22 065352](https://github.com/user-attachments/assets/ae2d293c-5653-4446-be51-1a3113c53862)
