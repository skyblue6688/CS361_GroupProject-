### A. Instruction for REQUESTING data from the implemented microservice.

1. The program creates a variable "mileage" that gets and stores the user input mileage.
2. The program uses a request that sends the data (a variable "miles" that includes the user input mileage) to the server.
3. The program uses JSON to send the data.
4. An example call to request data can be seen below, assuming the requested mileage is 10:

Code:
```
r = requests.post("http://127.0.0.1:3000/air_price", data={'miles': 10})
```
Example program receives the data from the microservice, which calculates the total flight price for the given mileage request:

Code:
```
data = r.json()
print(data[“total_price”])
```
### B. Instruction for RECEIVING data from the implemented microservice.

1. The program has a global variable that stores the price per mileage is 5 dollars/mile.
2. The program uses the POST method. Then in the result function, the variable "miles" receives and stores the mileage from requesting data, and converts the string to the integer.

   Code:
   ```
   miles = int(request.form['miles'])
   ```
4. The program uses arithmetic to calculate the total price (multiply miles and the price per mileage) and stores the result in the data.
5. The program uses JSON to send the data back.

   Code:
   ```
   return jsonify(data)
   ```
### C. UML sequence diagram showing how requesting and receiving data works.
<img width="885" alt="Screen Shot 2023-11-20 at 9 02 39 PM" src="https://github.com/skyblue6688/CS361_GroupProject-/assets/67412322/fd0d5a5a-ef93-4a0d-aa09-079ac0a30976">
