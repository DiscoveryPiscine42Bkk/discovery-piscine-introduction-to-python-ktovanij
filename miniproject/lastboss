class SmartFarmTaskOrganizer:
    def __init__(self):
        self.tasks = []
    
    def display_menu(self):
        """Display the main menu options"""
        print("\n**Smart Farm Task Organizer ---**")
        print("1. เพิ่มงานในฟาร์ม")
        print("2. แสดงรายการงานทั้งหมด")
        print("3. ลบงาน")
        print("4. สรุปจำนวนงานในแต่ละประเภท")
        print("5. ออกจากโปรแกรม")
    
    def add_task(self):
        """Add a new farm task"""
        print("\n**เพิ่มงานในฟาร์ม**")
        name = input("ป้อนชื่องาน: ")
        date = input("ป้อนวันที่ (dd/mm/yyyy): ")
        task_type = input("ประเภทงาน (พืชผัก/ปลู่สัตว์/อื่นๆ): ")
        
        task = {
            'name': name,
            'date': date,
            'type': task_type
        }
        
        self.tasks.append(task)
        print("เพิ่มงานสำเร็จ")
    
    def show_all_tasks(self):
        """Display all tasks in the list"""
        print("\n**รายการงานทั้งหมด:**")
        if not self.tasks:
            print("ยังไม่มีงานในรายการ")
            return
        
        for i, task in enumerate(self.tasks, 1):
            print(f"{i}. {task['date']} – {task['name']} ({task['type']})")
    
    def delete_task(self):
        """Delete a task from the list"""
        self.show_all_tasks()
        if not self.tasks:
            return
        
        try:
            task_num = int(input("\nลำดับของงานที่ต้องการลบ: ")) - 1
            if 0 <= task_num < len(self.tasks):
                deleted_task = self.tasks.pop(task_num)
                print(f"ลบงาน: {deleted_task['name']} แล้ว")
            else:
                print("ลำดับงานไม่ถูกต้อง")
        except ValueError:
            print("กรุณาป้อนตัวเลขเท่านั้น")
    
    def summarize_tasks(self):
        """Show summary of tasks by type"""
        if not self.tasks:
            print("\nยังไม่มีงานในรายการ")
            return
        
        type_counts = {}
        for task in self.tasks:
            task_type = task['type']
            type_counts[task_type] = type_counts.get(task_type, 0) + 1
        
        print("\n**สรุปจำนวนงานแต่ละประเภท:**")
        for task_type, count in type_counts.items():
            print(f"- {task_type}: {count} งาน")
    
    def run(self):
        """Main program loop"""
        while True:
            self.display_menu()
            choice = input("เลือกเมนู (1-5): ")
            
            if choice == '1':
                self.add_task()
            elif choice == '2':
                self.show_all_tasks()
            elif choice == '3':
                self.delete_task()
            elif choice == '4':
                self.summarize_tasks()
            elif choice == '5':
                print("\n**ขอบคุณที่ใช้โปรแกรม Smart Farm!**")
                break
            else:
                print("กรุณาเลือกเมนูระหว่าง 1-5 เท่านั้น")

if __name__ == "__main__":
    organizer = SmartFarmTaskOrganizer()
    organizer.run()
    
    