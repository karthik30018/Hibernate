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

** Note: It is triggering insert query instead of select query because**
- Laptop should have its own entity.
- What if one alien has multiple laptops.

### To overcome this the mapping concept was introduced.

# Mapping

## one-one Relationship
![WhatsApp Image 2025-05-23 at 07 06 57_d8d6e21d](https://github.com/user-attachments/assets/3f92fea6-efaa-4fda-90cd-161cdb40735a)

Example:

- Create a child entity(**Note: It should be an entity**)
![Screenshot 2025-05-28 063536](https://github.com/user-attachments/assets/0cbbebda-7d2a-4afc-8e29-c7f10ebd7c30)

- Create parent entity where you want to include child entity.
![Screenshot 2025-05-28 063940](https://github.com/user-attachments/assets/7be739ea-7845-4bb5-ac2e-5a8c8036f08c)

- In Main class include both the class like `.addAnnotatedClass(org.javaPro.Alien.class)
        .addAnnotatedClass(org.javaPro.Laptop.class).`
- And call the session.persist() method for both the classes.    
![Screenshot 2025-05-28 064049](https://github.com/user-attachments/assets/fcceab75-0501-46f7-a213-29d3c4c6e5b1)


## oneToMany and manyToOne Relationship

![WhatsApp Image 2025-05-23 at 07 09 19_5ac22b54](https://github.com/user-attachments/assets/ad1c1b95-4fbb-477a-b391-e100b66971f9)

![WhatsApp Image 2025-05-23 at 07 09 39_4b00ff04](https://github.com/user-attachments/assets/f2d08ca1-cbee-446c-9b76-ee66d2ab20a0)

![WhatsApp Image 2025-05-23 at 07 11 16_22f8e2ff](https://github.com/user-attachments/assets/026d2a07-d9e3-4096-be54-f581788d944b)

- or create one more table which should contain primary key of both tables.

- When ever we are working with a list we have to use onetomany or manytoone.

- ![Screenshot 2025-05-28 071235](https://github.com/user-attachments/assets/8ffda38e-2b97-48f0-a175-f40cbfc910f4)

- ![Screenshot 2025-05-28 071342](https://github.com/user-attachments/assets/1b04b252-1fea-4ad3-a503-8b38ef42f75d)
  
- ![Screenshot 2025-05-28 071431](https://github.com/user-attachments/assets/9d5bd9af-baa0-4ba4-9027-fb3f72a59da9)

- The above method will create seperate table
![Screenshot 2025-05-28 072027](https://github.com/user-attachments/assets/557be67e-7811-4250-9287-023b6c529e4b)

**To crate a reference in the same table/entity**

- ![Screenshot 2025-05-28 073312](https://github.com/user-attachments/assets/f33f38e5-dd4e-4a11-a999-9fe464afe41a)
-  ![Screenshot 2025-05-28 073534](https://github.com/user-attachments/assets/c9fe64f1-d339-43f3-b0bc-80a126444403)
-  ![Screenshot 2025-05-28 073737](https://github.com/user-attachments/assets/be925dbd-d004-441d-947e-d075a5619614)
-  In Laptop Entity it as created Alien reference. `alien_aid`
-  ![Screenshot 2025-05-28 074110](https://github.com/user-attachments/assets/065459b9-8739-4c32-8548-08d11c5adf75)


## manyToMany Relationship

![WhatsApp Image 2025-05-23 at 07 17 11_3b7b3f43](https://github.com/user-attachments/assets/2188c00f-4f20-49bd-9436-7866b82c44da)
![WhatsApp Image 2025-05-23 at 07 18 10_4e705364](https://github.com/user-attachments/assets/d25175c9-bf8c-4110-9063-23793354e91e)


- ![Screenshot 2025-05-29 072047](https://github.com/user-attachments/assets/9866c8e1-9209-4a19-a0cf-dc3f81a89c3c)
- ![Screenshot 2025-05-29 072229](https://github.com/user-attachments/assets/f1f8d680-c922-4e97-bf88-533bc08b2414)
- ![Screenshot 2025-05-29 072433](https://github.com/user-attachments/assets/4046c8a9-35f6-4da9-a8c4-f07b6b331c94)
- Mapping done by Alien Class
-![Screenshot 2025-05-29 072455](https://github.com/user-attachments/assets/87fce707-3de8-433f-bf46-0259e23e3418)

# Eager fetching and Lazy fetching 


- When we have a collection in an entity it uses *Lazy fetch* by default it will only print the query for the entity where we are using get statement.
- If are using the data then only it will fetch all the data
- Advantage : It won't load the entire data, will only load what the user want.
- ![WhatsApp Image 2025-06-02 at 16 31 57_cd2dfd26](https://github.com/user-attachments/assets/8e7ba670-23ff-4192-a0fc-bde1c184bc96)

- To make it *Eager fetch* `@OneToMany(fetch = FetchType.EAGER)`
- If we are using this even though we are not using it still it will call all the data.
- ![WhatsApp Image 2025-06-02 at 16 30 33_b7c605db](https://github.com/user-attachments/assets/d772fe8f-de40-4bb8-a308-8f5860fad0e8)


# Hibernate Caching

- In a session if we are calling same data from the client side again and again it won't call it from the database instead the hiberante provide caching, where the session data will be stored untill the session is closed.
- Disadvantage: what if the data changes due to some activities.
- The hibernate provides when to use caching and when not to use is called **L1 cache**

- For **L2 Cache** we have to use external tool which enable use to use same data in multiple session JCache -> EHCACHE,Caffeine.


# HQL (Hibernate Query Language)

## Fetching data using HQL

- To fetch all the data
![Screenshot 2025-06-02 184700](https://github.com/user-attachments/assets/9bb54ce4-ee77-4432-90e3-9cea7790fd15)

-Using where clause
![Screenshot 2025-06-02 185221](https://github.com/user-attachments/assets/4efd44f7-c9c3-401d-8e35-b91222242324)

- Passing parameter
![Screenshot 2025-06-02 191128](https://github.com/user-attachments/assets/5f4b126d-5816-4fb6-9aa4-66a10d51bebc)

- Perticular columns
![Screenshot 2025-06-02 215856](https://github.com/user-attachments/assets/d7c45740-8c51-4c09-af8d-a515a3122e0c)

# Get vs Load

## get (Eager loading)

- When using get method if we didn't call the data then also the query will get executed.

- When calling
- ![Screenshot 2025-06-02 222729](https://github.com/user-attachments/assets/377ce935-a60b-471d-95cb-d1eb1aa87c91)

- When it is not called
- ![Screenshot 2025-06-02 222903](https://github.com/user-attachments/assets/c6e28ead-f23f-4cfc-8cf9-5ffaff4d88f0)

## load (lazy loading)

- When the data is called then only the query is executed.

- When data is called
- ![Screenshot 2025-06-02 223108](https://github.com/user-attachments/assets/a4beaa01-a204-4afe-8568-2b38b761e354)
or
- ![Screenshot 2025-06-02 223356](https://github.com/user-attachments/assets/f3463e3e-3d60-4170-b72e-85cbb69e77b5)


- When calling the data
- ![Screenshot 2025-06-02 223211](https://github.com/user-attachments/assets/4c005962-f0d9-4072-a310-a2c29eeba4e1)
 or
- ![Screenshot 2025-06-02 223321](https://github.com/user-attachments/assets/07e7140b-9dd1-434e-bffa-fe6fa6e535af)

# L2 Cache using Ehcache

- We have created 2 session still L2 level cache is not applied.
- ![Screenshot 2025-06-02 224032](https://github.com/user-attachments/assets/6f4963d4-f902-4d51-9a42-62efd28691eb)

Use @Cacheable under @Entity and add dependencies in maven related to Ehcache
- ![Screenshot 2025-06-02 225126](https://github.com/user-attachments/assets/3db5604d-e1ec-40fc-a778-133db18a6248)


