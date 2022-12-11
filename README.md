# Number-Guessing-Game-
this project is made by using Python language 
'''mini project of python (K22MB-INT108) to take pick out random number and
check the number is positive/negative, odd/even and prime/composite'''
'''THIS ADVACE FORM OF MINI PROJECT'''

import random
try:
    class mini_project():
        def introduction(self):
            '''This projected was created on 31-october-2022 by ............. for
            mini project !st semister   of python project on the topic "To take
            random number and diplay its properties" '''
            print("\t\t WELCOME TO NEW PROJECT OF PYTHON")
            print('''\t     NOTE, if you can guess the no. within 10
                steps then only you can get properties of number..''')
            print('-----------------------------------------------------------------------------\n')
            
        def head(self,num1,num2,count):
            '''It has given name 'head' function, it includes the range from -infinitive to +infinitive i.e
            according to user choice'''
            self.num1=num1
            self.num2=num2
            self.count=count
            
        def rand_num(self):
            '''It takes a random number from certain number to a particular number
            as provided by the user '''
            rand=random.randint(self.num1,self.num2)
            self.rand=rand
            
        def body(self,yourChoice):
            '''It is body part of coding, it includes all main part of coding from guessing
            the number to providing the properties of number (-ve/+ve even/odd prime/composite) as guessed by the user'''
            self.yourChoice=yourChoice
            
            for i in range(1,15):
                if i<=5:
                    if self.yourChoice < self.rand:
                        print(f'**Please enter higher number than {self.yourChoice}** \n')
                        self.yourChoice=int(input('Enter a number: '))
                        self.count +=1
                        
                    if self.yourChoice > self.rand:
                        print(f'**Please enter lower number than {self.yourChoice}** \n')
                        self.yourChoice=int(input('Enter a number: '))
                        self.count +=1
                        
                    if self.yourChoice == self.rand:
                        print(f'congratulations !!! you guess the number in {self.count} step only \n')
                        #from here the coding of properties of number is included
                        print(f'Properties of number {self.yourChoice} are.. ')
                        print('--------------------------------------------')
                        
                        #to check negative or positive
                        if self.yourChoice <0:
                            print(self.yourChoice,'negative number')
                            print(self.yourChoice,'is nither eve/odd nor composite/prime')
                            
                        if self.yourChoice ==0:
                            print(self.yourChoice,'is Zero ')
                            print(self.yourChoice,'is neither prime/composite nor even/odd')
                            
                        if self.yourChoice >0:
                            print(self.yourChoice,'is a poitive number')
                            
                            #to check  even odd 
                            if self.yourChoice %2 == 0:
                                print(self.yourChoice,'is a even number')
                                
                                #to check prime composite
                                for i in range(2,self.yourChoice):
                                    if self.yourChoice % i ==0:
                                        print(self.yourChoice,'is a composite number')
                                        break
                                    else:
                                        print(self.yourChoice,'is a prime number')
                                        break
                                    
                            else:
                                print(self.yourChoice,'is a odd number')
                                for i in range(2,self.yourChoice):
                                    if self.yourChoice % i ==0:
                                        print(self.yourChoice,'is a composite number')
                                        break
                                    else:
                                        print(self.yourChoice,'is a prime number')
                                        break
                                

                            
                        break
                else:
                    print('''\n\t
                            <><><><><><><><><><><><><><>
                    ^-----GAME OVER.......TRY AGAIN-----^
                            <><><><><><><><><><><><><><>''')
                    break

                    
                        
    call=mini_project()
    call.introduction()

    while True:
        play=int(input('''
        DO YOU WANT TO PLAY GAME, enter
            1 Yes
            2 No | Exit
                    '''))
        if play ==1: 
            num1=int(input('Enter a number to start the range: '))
            num2=int(input('Enter a number to terminate the range:  '))
            call.head(num1,num2,1)
            call.rand_num()
            print()
            yourChoice=int(input(f'Guess the number from {num1} to {num2}: '))
            call.body(yourChoice)
        else:
            print('\n\n\t\t!!!"""*BEST OF LUCK*"""!!!')
            break
except Exception as e:
    print('\n\t\t **PLEASE CHECK ERROR IS OCCURED**')
    print('\t     ',e)

