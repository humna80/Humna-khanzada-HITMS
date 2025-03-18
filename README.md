#include <iostream>
using namespace std;
bool login() {
string username, password;
cout<<"Enter Username: ";
cin>> username;
cout<<"Enter Password: ";
cin>> password;
if(username == "admin" && password == "12345") {
cout<<"Login Successful!\n\n";
return true;
}else{
cout<<"Invalid Details. Try again!\n";
return false;
}
}
void startQuiz(){
string questions[]={
"What is the capital of France?",
"Which data type is used to store whole numbers in C++?",
"What is 5 + 3 * 2?",
"Which planet is known as the Red Planet?",
"Who wrote 'Hamlet'?"
};
string options[][4] = {
{"A) Berlin", "B) Madrid", "C) Paris", "D) Rome"},
{"A) float", "B) int", "C) char", "D) string"},
{"A) 16", "B) 11", "C) 10", "D) 13"},
{"A) Earth", "B) Mars", "C) Jupiter", "D) Venus"},
{"A) Charles Dickens", "B) William Shakespeare", "C) J.K. Rowling", "D) Jane Austen"}
};
char correctAnswers[] = {'C', 'B', 'B', 'B', 'B'};
int totalQuestions = 5;
int score = 0;
char userAnswer;
cout<<"                                               -----QUIZ STARTS NOW-----\n\n";
for(int i = 0; i < totalQuestions; i++) {
cout<<"Q"<<(i + 1)<<". "<<questions[i]<<"\n";
for(int j = 0; j < 4; j++){
cout<<options[i][j]<<"\n";
}
cout<<"Your Answer (A/B/C/D): ";
cin>> userAnswer;
userAnswer = toupper(userAnswer);
if(userAnswer == correctAnswers[i]){
cout<<"Correct!\n\n";
score++;
}else{
cout<<"Wrong! Correct Answer: "<<correctAnswers[i]<<"\n\n";
}
}
cout<<"                                                 ---- QUIZ ENDED ----\n";
cout<<"Your Score: "<<score<<"/"<<totalQuestions<<"\n";
if(score == totalQuestions){
cout<<"Excellent! Your all answers are correct.\n";
}else if(score>=3){
cout<<"Good Job! Keep learning.\n";
}else{
cout<<"You need more hard work!\n";
}
}
int main(){
cout<<"                                              -------ONLINE QUIZ SYSTEM --------\n";
while(!login());
startQuiz();
return 0;
}
