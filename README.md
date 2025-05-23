# Hibernate

## Creating a table and inserting values to the database (Create)

### Step 1: Create a class with getters , settres and toString()
![Screenshot 2025-05-22 062106](https://github.com/user-attachments/assets/1b61ec84-8a52-4cbc-990d-43d24060ea72)
- @Entity represents table
- @Id represents primary key
- In '.addAnnotatedClass(Class_Path)`
### Step 2: Create `hibernate.cfg.xml` page
- `<property name="hibernate.hbm2ddl.auto">update</property>` - It will update the existing table, if table is not present then it will create new table.
- `<property name="hibernate.hbm2ddl.auto">create</property>` - It will create new table, if exist then it will drop the existing table and creates new table.
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


## Creating same table with different name

![Screenshot 2025-05-22 071816](https://github.com/user-attachments/assets/3324d204-83c7-4465-97df-f133955d9f0a)

## Changing table name

![Screenshot 2025-05-22 071921](https://github.com/user-attachments/assets/a0f2f3d3-8c3e-4e97-8182-d30c6d9e01cf)

## Changing column name

![Screenshot 2025-05-22 072101](https://github.com/user-attachments/assets/566d9725-c0dc-40c8-bfe4-4cb7c3af1494)

- `@Transient` - If we dont wanna sava the data of the perticular field but we want that field in the class.

# Embeddable

- `@Embeddable` is used to embed one class into another class and create the table structure
like below
![WhatsApp Image 2025-05-23 at 06 18 18_e775e8aa](https://github.com/user-attachments/assets/eabe0741-7c7f-4673-8026-ed6713cd100c)  

![Screenshot 2025-05-23 063236](https://github.com/user-attachments/assets/ca1382dd-db6e-429f-a390-4f12be65383d)

![Screenshot 2025-05-23 063314](https://github.com/user-attachments/assets/85dbe467-96c6-4884-a139-26a58ba6e277)

![Screenshot 2025-05-23 063443](https://github.com/user-attachments/assets/9bf06b57-8e9f-456e-893f-c6ab0eaaa33e)

- To retrieve the data

![Screenshot 2025-05-23 064054](https://github.com/user-attachments/assets/c44ae8bf-d92f-4934-9bbd-3b35bab8ae15)

![Screenshot 2025-05-23 064244](https://github.com/user-attachments/assets/907e67aa-de82-455d-afd1-23f277c8125b)

** Note: It is triggering insert query instead of select query **
