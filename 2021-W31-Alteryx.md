# Preppin Data 2021 Week 31 - Alteryx Solution

#### Solution by Luis Garcia Fuentes
#### For more details on this weekly challenge visit [Preppin Data](https://preppindata.blogspot.com/)

## Excelling in Prep Challenge

### Details

The weekly sales of Bike Components from Preppin's bike store Allchains is what we are analysing. The returns are where the product has been deemed faulty before it's sold. 

![Sample input data](https://1.bp.blogspot.com/-dk0JLWbsnSc/YQl4-TLNElI/AAAAAAAACO4/4Rpsr-zZ5HoSqyYShmxv0pgfUwb-fgguwCLcBGAsYHQ/s1130/Screenshot%2B2021-08-03%2Bat%2B18.11.28.png)

### Requirements
- Input data
- Remove the 'Return to Manufacturer' records
- Create a total for each Store of all the items sold
- Aggregate the data to Store sales by Item
- Output the data

### Expected Output

![How the output should look](https://1.bp.blogspot.com/-zAcqRtDPLE0/YQl8uhM-dUI/AAAAAAAACPA/Q5_ORFfX0pI6KNOr5q4qAPPadn30PtRpgCLcBGAsYHQ/w640-h108/Screenshot%2B2021-08-03%2Bat%2B18.28.07.png)

## My Solution

1. Input the data
2. Filtered out the items where the status did not equal "Return to manufacturer"
3. Changed the "Number of Items" field from a string to an integer for use in future steps

![The first three basic steps](https://user-images.githubusercontent.com/74035071/128637465-fb5d0c7d-ac6c-4a3c-ae0f-6bf3663dd212.png)

4. Used the Cross Tab tool to separate the "Items" column into separate columns per distinct item

![image](https://user-images.githubusercontent.com/74035071/128637503-2bb646ef-1b64-4fd2-9e13-8f6661ee8f75.png)
* At this point you have half of the solution, only the total items sold per store are needed
![image](https://user-images.githubusercontent.com/74035071/128637546-6a7f06e1-77dc-4f67-b5bd-a880218a5f08.png)
5. I used the Tranpose column to turn the separate item columns back into one column containing the number of items sold

![image](https://user-images.githubusercontent.com/74035071/128637673-056c0d8d-e147-415c-9b59-ef683f321a32.png)

6. Used the summarize function to sum the number of items sold per store

![Tool Configuration](https://user-images.githubusercontent.com/74035071/128637688-0d9c63dd-9c25-4066-a6c8-5395659a6dd4.png)
![Items sold per store](https://user-images.githubusercontent.com/74035071/128637698-3faf8a29-ed1d-4732-a470-543d6637e13a.png)


7. Joined the Items sold per store to the output of Step 4 

![image](https://user-images.githubusercontent.com/74035071/128637732-a16beb23-5269-4cb7-bf2b-9a51ff465baa.png)

8. Results

![image](https://user-images.githubusercontent.com/74035071/128637745-45a8754c-54a4-4be3-9dd7-9a69feb4762b.png)

### Full Workflow 

![image](https://user-images.githubusercontent.com/74035071/128637773-2d3cbcfd-dd3f-452f-b685-dd41be95f6bd.png)

