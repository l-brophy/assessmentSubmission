# Database Challenges

## Question 2

```sqlite
UPDATE Employees
SET Email = SUBSTR(Email, 1, INSTR(Email, '@')) || 'company' || SUBSTR(Email, INSTR(Email, '.'))
WHERE Email IS NOT NULL
```

# Back-End Code Challenges

## Question 1


```csharp
public static string Likes(List<string> likes)
{
	int i = likes.Count;

	if (i == 0)
		// early returns for flat and flowy logic
		return "No one likes this.";
			
	if (i == 1)
		return $"{names[0]} likes this.";

	if (i == 2)
		return $"{names[0]} and {names[1]} like this.";

	if (i == 3)
        return $"{names[0]}, {names[1]} and {names[2]} like this.";

    return $"{names[0]}, {names[1]} and {i - 2} others like this.";
}
```

## Question 2


```csharp
public class Factory
{
    private RobotService _robotService;
    private PartsService _partsService;
    private CarService _carService;
    
    public Factory(RobotService robotService, PartsService partsService)
    {
        _robotService = new RobotService();
        _partsService = new PartsService();
        _carService = new CarService();
    }

    public Robot BuildRobot(Enum RobotType)
    {
		var parts = GetRobotPartsFor(RobotType);
		// decouple BuildRobot methods from RobotType
        return _robotService.BuildRobot(RobotType, parts);
    }

    public Car BuildCar(Enum CarType)
    {
        var parts = GetCarPartsFor(CarType);
        // CarType param in lieu of conditional
        return _carService.BuildCar(CarType, parts);
    }

    public List<Parts> GetRobotPartsFor(Enum RobotType)
    {
        return _partsService.GetParts(RobotType);
    }

    public List<Parts> GetCarPartsFor(Enum CarType)
    {
        return _partsService.GetParts(CarType);
    }
}
```

# Front-End Code Challenges

## Question 1

firstDiv will be red, secondDiv will be orange.

```javascript
document.getElementById('firstDiv').style.backgroundColor='pink';
```

```javascript
document.getElementById('secondDiv').classList.add('yellow-card');
```

Or, abstracted into a function for better readability and modularity:

```javascript
function pinkify(id) {
	let elem = document.getElementById(id);
	elem.style.backgroundColor = 'pink'; 
}
```

## Question 2

1. == in JS converts the values on either side to the same data type before it compares them, so 5 and "5", once either one is type-cast, are equal. It is not strict.
2. Using the strict === instead. 

## Question 3

1. Using breakpoints and writing classes with different settings which take precedent when using the applicable viewports, e.g., what would have been a sidenav on desktop becomes a hamburger menu on mobile because there is not enough space on the viewport for the main content and the sidenav. 
2. Bundled JavaScript improves performance - load time and caching - and the order that multiple files would load in, which can be very problematic, does not have to be a concern at all.
3. Sass needs to be compiled to a CSS file, which needs to be referenced as the stylesheet in your HTML. 
4. By testing JavaScript on various browsers and versions to ensure it runs or be able to pinpoint why it doesn't, writing fallbacks, using feature detection as a conditional, or writing your own versions of newer functionality. 
