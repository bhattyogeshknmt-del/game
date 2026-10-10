import streamlit as st
import random

st.set_page_config(page_title="Raja Goli Saap Game", page_icon="👑")

st.title("👑 Raja Goli Saap Game")
st.write("**Rules:** Raja > Goli | Goli > Saap | Saap > Raja")

choices = ["raja", "goli", "saap"]

if 'user_score' not in st.session_state:
    st.session_state.user_score = 0
if 'computer_score' not in st.session_state:
    st.session_state.computer_score = 0

user_choice = st.selectbox("Choose your option:", choices)

if st.button("Play!"):
    computer_choice = random.choice(choices)
    
    col1, col2 = st.columns(2)
    col1.metric("You Chose", user_choice.upper())
    col2.metric("Computer Chose", computer_choice.upper())

    if user_choice == computer_choice:
        st.info("🤝 Tie!")
    elif (user_choice == "raja" and computer_choice == "goli") or \
         (user_choice == "goli" and computer_choice == "saap") or \
         (user_choice == "saap" and computer_choice == "raja"):
        st.success(f"You Win! {user_choice.capitalize()} beats {computer_choice.capitalize()}")
        st.session_state.user_score += 1
    else:
        st.error(f"You Lose! {computer_choice.capitalize()} beats {user_choice.capitalize()}")
        st.session_state.computer_score += 1

st.divider()
st.subheader(f"Score - You: {st.session_state.user_score} | Computer: {st.session_state.computer_score}")

if st.button("Reset Score"):
    st.session_state.user_score = 0
    st.session_state.computer_score = 0
    st.rerun()
