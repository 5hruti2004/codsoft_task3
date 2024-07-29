# codsoft_task3

contact={}


def view_contact():
    print("Name \t \tContact Number")
    for key in contact:
        print("{}\t\t{}".format(key,contact.get(key)))
while True:
    ch= int(input(" 1.Add Contact\n 2.View contact\n 3.Search Contact\n 4.Update contact\n 5.Delete contact\n 6.Exit\n Enter your choice: "))
    if ch == 1:
            name= input("Enter the contact name: ")
            Phone= input("Enter the phone number: ")
            Email= input("Enter the email id: ")
            Address= input("Enter the address: ")
            contact[name]=Phone
                  
    elif ch == 2:
            if not contact:
                    print(" No list Found")
            else:
                view_contact()
    elif ch == 3:
            search_name= input("Enter the contact name: ")
            if search_name in contact:
                        print(search_name,"'s contact number is ",contact[search_name])
            else :
                 print("Data Not Found")
                              
    elif ch == 4:
            update_contact = input(" Enter the contact name to be updated: \n")
            if update_contact in contact:
                        Phone= input(" Enter phone number: \n")
                        contact[update_contact]=Phone
                        view_contact()
            else:
                print("Data Not Found")
    elif ch == 5:
            delete_contact=input("Enter the contact to be deleted: ")
            if delete_contact in contact:
                        confirm =  input("Are you sure delete this contact yes/no ?\n")
                        if confirm =='yes' or confirm=='Yes':
                                contact.pop(delete_contact)
                        view_contact()
            else:
                print("Data Not Found")
    else:
        break
