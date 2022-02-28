# Disk-Stress-Test-DST-
Information worth taking a look at:

Images:![image](https://user-images.githubusercontent.com/89658050/156052916-da186a7e-6c4d-4d6c-816d-74e63f417bc9.png)


Source code (NOTE: some important things like AI's and the main code for the dst is put under '...' to avoid copywrite)

try:
    import colorama
    import time
    import os
    import threading
    import shelve
    from random import randint
    import webbrowser
except Exception:
    input("An error occured while bounding modules to this program. please press ENTER for now: ")
    quit()

BLACK = '\u001b[30m'
RED = '\u001b[31m'
GREEN = '\u001b[32m'
YELLOW = '\u001b[33m'
BLUE = '\u001b[34m'
MAGENTA = '\u001b[35m'
CYAN = '\u001b[36m'
WHITE = '\u001b[37m'
RESET = '\u001b[0m'

BOLD = '\u001b[1m'
UNDERLINE = '\u001b[4m'
REVERSE = '\u001b[7m'

core_count = 0
name = 0
pt = 0
jobbs = 0
last_time = float(0)
total_time = float(0)
lt = float(0)
responce = None

def colour_print(text: str, effect: str) -> None:
    """
    Print `text` using the ANSI sequences to change colour, etc

    :param text: The text to print.
    :param effect: The effect we want.  One of the constants
        defined at the start of this module.
    """
    output_string = "{0}{1}{2}".format(effect, text, RESET)
    print(output_string)

def _colour(text: str, effect: str):
    """
    For the main code output
    :param text: Enter text to print
    :param effect: The effect that is required
    :return:
    """
    colorama.init()
    colour_print(text, effect)
    colorama.deinit()

def adder(times):
    global name
    global jobbs
    global last_time
    global total_time
    global lt

    try:
        test = shelve.open("DST(DO-NOT-DELETE).txt", "w")
        test.close()
    except Exception:
        test = shelve.open("DST(DO-NOT-DELETE).txt", "c")
        test.close()

    for i in range(times):
        a = time.time()

        random_number = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number2 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number3 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number4 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number5 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number6 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number7 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number8 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number9 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
        random_number10 = randint(0,10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)

        x = shelve.open("DST(DO-NOT-DELETE).txt", "w")

        x[str(random_number)] = [random_number]
        x[str(random_number2)] = [random_number2]
        x[str(random_number3)] = [random_number3]
        x[str(random_number4)] = [random_number4]
        x[str(random_number5)] = [random_number5]
        x[str(random_number6)] = [random_number6]
        x[str(random_number7)] = [random_number7]
        x[str(random_number8)] = [random_number8]
        x[str(random_number9)] = [random_number9]
        x[str(random_number10)] = [random_number10]
        x.sync()
        b = time.time()
        answer = b-a
        if answer < last_time:
            last_time = b-a
        else:
            pass
        lt = b-a
        total_time += b-a
        name += 1
        os.system("color fc")
        print("Current job {} ; Time {}".format(name, lt))


def threads(thread, jobs_count):
    global pt
    if thread == 10:
        total = jobs_count
        jobs_count /= 10
        jobs_count = int(jobs_count)
        pt = jobs_count
        thread1 = threading.Thread(target=adder(jobs_count))
        thread2 = threading.Thread(target=adder(jobs_count))
        thread3 = threading.Thread(target=adder(jobs_count))
        thread4 = threading.Thread(target=adder(jobs_count))
        thread5 = threading.Thread(target=adder(jobs_count))
        thread6 = threading.Thread(target=adder(jobs_count))
        thread7 = threading.Thread(target=adder(jobs_count))
        thread8 = threading.Thread(target=adder(jobs_count))
        thread9 = threading.Thread(target=adder(jobs_count))
        thread10 = threading.Thread(target=adder(jobs_count))


        thread1.start()
        thread2.start()
        thread3.start()
        thread4.start()
        thread5.start()
        thread6.start()
        thread7.start()
        thread8.start()
        thread9.start()
        thread10.start()

        thread1.join()
        thread2.join()
        thread3.join()
        thread4.join()
        thread5.join()
        thread6.join()
        thread7.join()
        thread8.join()
        thread9.join()
        thread10.join()

def main_point():
    _colour("This project is made by Rowexe, github page: https://www.github.com/Rowexe", BOLD)
    redirection = input("Do you want to be redirected?(y/n): ")

    if redirection.lower() == "y":
        webbrowser.open_new_tab("https://www.github.com/Rowexe")
    else:
        pass
    
main_point()

try:
    os.system("color fc")
except Exception:
    pass

try:
    core_count = os.cpu_count()
except Exception:
    core_count = 3

while True:
    try:
        os.system("color fc")
    except Exception:
        pass
    print()
    jobs = input("Please enter jobs (the higher the jobs, the more stress is put upon the disk) ; 'q' to quit: ")

    if jobs.lower() == "q":
        quit()
    else:
        try:
            jobs = int(jobs)
            jobbs = jobs
            try:
                os.system("color fc")
            except Exception:
                pass
            _colour("Laid {} jobs with the PID {}".format(jobbs, os.getpid()), CYAN)
            time.sleep(2)
            threads(10, jobs)
            for i in range(0,11):
                print()
            _colour("RESULTS: ", YELLOW)
            _colour("\r Total jobs per thread {} ; Completed jobs {} ; Time {} per job (minimum); Total time for job("
                    "s) {}".format(pt, jobbs, last_time, total_time), BOLD)
            print()
            _colour("AI responce:", BOLD)
            print()
            _colour("Category (high to low): ", YELLOW)
            _colour("1) Very fast", YELLOW)
            _colour("2) Fast", YELLOW)
            _colour("3) Medium", YELLOW)
            _colour("4) Slow", YELLOW)
            _colour("5) Very slow", YELLOW)
            print()
            timer = int(total_time/jobbs*100)
            if timer > 5 or timer == 5:
                responce = "Very slow"
            elif timer == 4:
                responce = "Slow"
            elif timer == 3:
                responce = "Medium"
            elif timer == 2:
                responce = "Fast"
            elif timer == 1 or timer == 0:
                responce = "Very fast"

            _colour("Responce: {}".format(responce), YELLOW)

            print()
            clear = input("Do you want to clear logs/file this program has created during the test? (y/n): ")
            if clear.lower() == "y":
                try:
                    try:
                        f1 = os.path.getsize("DST(DO-NOT-DELETE).txt.dat")
                        f2 = os.path.getsize("DST(DO-NOT-DELETE).txt.dir")
                        f3 = os.path.getsize("DST(DO-NOT-DELETE).txt.bak")
                        total = f1+f2+f3
                    except Exception:
                        total = "Undetectable"
                    _colour("Deleting files, total size {} bytes".format(total), YELLOW)
                    os.remove("DST(DO-NOT-DELETE).txt.dat")
                    os.remove("DST(DO-NOT-DELETE).txt.dir")
                    os.remove("DST(DO-NOT-DELETE).txt.bak")
                    _colour("Deleted!", YELLOW)
                except Exception:
                    try:
                        os.remove("DST(DO-NOT-DELETE).txt.dir")
                        os.remove("DST(DO-NOT-DELETE).txt.bak")
                        os.remove("DST(DO-NOT-DELETE).txt.dat")
                    except Exception:
                        try:
                            os.remove("DST(DO-NOT-DELETE).txt.bak")
                            os.remove("DST(DO-NOT-DELETE).txt.dat")
                            os.remove("DST(DO-NOT-DELETE).txt.dir")
                        except Exception:
                            _colour("An error occured while deleting files", RED)
            else:
                pass



        except Exception:
            _colour("Please enter a integer number ONLY! : 2 second wait before continue", YELLOW)
            time.sleep(2)
            continue
          
