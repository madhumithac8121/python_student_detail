# python_student_detail
import cvs

def write_info_cvs(info_list):
    with open('student_info.cvs','a',newline=' ') as cvs_file:
        writer=cvs.writer(cvs_file)

        if cvs_file.tell()==0:
            writer.writer_row(["Name", "Age", "Phone_Number", "Address", "email_id"])

        writer.writer_row(info_list)

if _name_=='_main_':
    condition = True
    student_num = 1

    while(condition):
        student_info = input("Enter the student detail #{}: ".format(student_num))

        student_info_list = student_info.split(' ')
        print("\n The entered information is \nName: {}\nAge: {}\nPhone_Number: {}\nAddress: {}\nemail_id: {} ".format(student_info_list[0],student_info_list[1],student_info_list[2],student_info_list[3],student_info_list[4] ))

        choise_check = input("IS entered value is right (yes/no): ")
        if choise_check == "yes":
            write_info_cvs(student_info_list)

            condition_check = ("Enter yes if you want to enter addtitional student information: ")
            if condition_check == "yes":
                condition = True
                student_num = student_num + 1
            elif condition_check == "no":
                condition = False
        elif choise_check == "no":
            print("\nPlease re-enter the values: ")
        
        

