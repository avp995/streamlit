import streamlit as st
import random
import altair as alt
import numpy as np
import pandas as pd
import yfinance as yf

st.write("""
#Stock Price 
Graph of Appl Stock Prices 
""")

#ticker symbol 
tickerSymbol = 'AAPL'

#Get the information for the ticker 
tickerData = yf.Ticker(tickerSymbol)

#Get the data about the prices for the ticker 
tickerDf = tickerData.history(period='1d', start='2015-5-31', end='2020-5-31')

st.line_chart(tickerDf.Close)
st.line_chart(tickerDf.Volume)
