# bakery-machine-control
class BakeryMachine:
    def __init__(self):
        self.temperature = 180  # Default baking temperature in Celsius
        self.timer = 20  # Default baking time in minutes
        self.status = "Idle"

    def preheat_oven(self, temp):
        """Set the oven to a specified temperature."""
        self.temperature = temp
        self.status = f"Preheating oven to {temp}°C"
        print(self.status)

    def set_timer(self, time):
        """Set the baking time."""
        self.timer = time
        print(f"Baking time set to {time} minutes")

    def start_baking(self):
        """Start the baking process."""
        if self.status.startswith("Preheating"):
            self.status = "Baking in progress"
            print("Baking started...")
        else:
            print("Please preheat the oven first!")

    def check_status(self):
        """Check the current status of the machine."""
        print(f"Current status: {self.status}")

    def finish_baking(self):
        """Complete the baking process."""
        self.status = "Baking completed. Remove buns."
        print(self.status)

# Example Usage
machine = BakeryMachine()
machine.preheat_oven(200)
machine.set_timer(25)
machine.start_baking()
machine.check_status()
machine.finish_baking()
