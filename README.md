import time
import random
import datetime
def wishher():
    hour=int(datetime.datetime.now().hour)
    if hour>=0 and hour<12:
        speak("good moning yukta")
    elif hour>=12 and hour<18:
        speak("good afernoon yukta")
    else:
        speak("good evening yukta")
def speak(str):
    from win32com.client import Dispatch
    speak=Dispatch("SAPI.SpVoice")
    speak.speak(str)
if __name__=='__main__':
    wishher()
    speak("hey yukta, i am piyush, i have designed the game as stone, paper, sesior....")
    lis=["stone","paper","sesior"]
    print("Welcome stone,paper,sesior GAME")
    time.sleep(2)
    speak("in this game you have 5 lifes only")
    print("\nyou have 5 lifes")
    a=0
    b=0
    for i in range(5,0,-1):
        comp = random.choice(lis)
        print("\nlifes left",i)
        print("choose anything from stone,paper,sesior")
        you = str(input("your input:\n"))


        if you!=comp:
            if you=="stone" and comp=="paper":
                print("comp had chossen paper")
                print("comp wins")
                a=a+1
                speak(f"comp score is {a} and your score is {b}")
            elif you=="paper" and comp=="sesior":
                print("comp had chossen sesior")
                print("comp wins")
                a=a+1
                speak(f"comp score is {a} and your score is {b}")
            elif you=="sesior" and comp=="stone":
                print("comp had chossen stone")
                print("comp wins")
                a=a+1
                speak(f"comp score is {a} and your score is {b}")

            elif comp == "stone" and you == "paper":
                print("you wins")
                b=b+1
                speak(f"comp score is {a} and your score is {b}")
            elif comp == "paper" and you == "sesior":
                print("you wins")
                b=b+1
                speak(f"comp score is {a} and your score is {b}")
            elif comp == "sesior" and you == "stone":
                print("you wins")
                b=b+1
                speak(f"comp score is {a} and your score is {b}")
        else:
            print("comp and you have chossen same")
            print("Draw")
            speak(f"comp score is {a} and your score is {b}")
    print("game over")
    print("result time")
    time.sleep(2)
    print(f"you have won {b} times in game")
    print(f"while comp have won {a} times in game")

    if a>b:
        print("\n   ********comp wins********    ")
        speak(f"oh sorry but comp wins you loss")
    elif a<b:
        print("\n     *******you wins*******      ")
        speak(f"congratulations, you have won the game")
    else:
        print("The Match is draw")
        speak("due to your and computer score matches the match is draw")
    speak("thank you ,have a good day,bye")
