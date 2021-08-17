# credit-card-validtors
#its help to validate credit numbers


ab=(input('Enter a card number:').strip())
while ab.isalpha():
    print('please only enter a digit')
    break
else:
    card_no=list(ab)

    check_digit=card_no.pop()

    card_no.reverse()
    even_list=[]
    for index,digit in enumerate(card_no):
        if index%2==0:
            double_even=int(digit)*2
            if double_even>9:
                double_even=double_even-9

            even_list.append(double_even)
        else:
            even_list.append(int(digit))


    total=int(check_digit)+sum(even_list)
    if total%10==0:
        print('card is legit')
    else:
        print('enter a valid card')
