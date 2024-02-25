import time
def ask_que(question,options,correct_option):
# display the question and answer chocies
print(question)
for i,option in enumerate(options, 1):
        print(f"{i}. {option}")
#get user input for  the answer 
    user_answer = input("Your answer (enter the option number):")
# Validate user input
    if user_answer.isdigit() and 1 <= int(user_answer) <= len(options):
        user_answer = int(user_answer)
# Check if the user's answer is correct
        if options[user_answer - 1]== correct_option:
           print("Correct!")
            return 1
        else:
            print(f"Wrong! The correct answer is:{correct_option}")
            return 0
             else:
        print("Invalid input. Please enter a valid option.")
        return 0
def run_quiz(questions):
    total_score = 0
# Iterate through each question in the quiz
    for q in questions:
        question_text, options, correct_option = q
# Ask the current question and update the total score
        total_score += ask_question(question_text, options, correct_option)
# Add a newline for better readability between questions
        print()
        return total_score
def main():
    print("Welcome to the Python Quiz Game!")
    time.sleep(1)  # Pause for a moment
  # Define the quiz questions with their options and correct answers
    quiz_questions = [(What is the capital of France?", ["Berlin", "Paris", "Madrid"], "Paris"),
        ("Which programming language is this game written in?", ["Java", "Python", "C++"], "Python"),
        ("What is 2 + 2?", ["3", "4", "5"], "4"),]
# Run the quiz and get the user's total score
    user_score = run_quiz(quiz_questions)
# Display the user's total score at the end of the quiz
    print(f"\nQuiz completed! Your total score is: {user_score}")
if _name_ == "_main_":
    main()
