# javascript-closure-and-class-example
Example of using closures and classes together

```javascript
function createCar() {
  let carID = 0;
  
  return class {
    constructor(make, model, insurancePrice) {
      this.make = make;
      this.model = model;
      this.insurancePrice = insurancePrice;
      this.carID = ++carID;
    }
 
    insurancePremium(interest) {
      return interest * this.insurancePrice;
    }
    
    getCarInformation(interest) {
       const formattedInterest = `$${this.insurancePremium(interest)}`
       
       console.log(`Car ID: ${this.carID} - ${this.make} ${this.model}`);
    }
    
  }
}

const carMaker = createCar();
const honda = new carMaker("Honda", "Type R", 150)
const golf = new carMaker("VW", "Golf GTI", 125)
const porsche = new carMaker("Porsche", "911 GT4", 500)


honda.getCarInformation(4); //CAR ID : 1
golf.getCarInformation(4); //CAR ID : 2
porsche.getCarInformation(4); //CAR ID : 3

```
