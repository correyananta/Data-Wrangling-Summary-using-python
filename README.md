# Introduction-and-Data-Wrangling-Summary-using-python
In this section, you will learn how to approach data acquisition in various ways, and obtain necessary insights from a dataset. By the end of this lab, you will successfully load the data into Jupyter Notebook, and gain some fundamental insights via Pandas Library.

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h1 align=center><font size=50>Data Analysis with Python</font></h1></p>
<p><h2 align=center><font size=5>Introduction and Data Wrangling Summary</font></h2></p>
<h3 align=center><font size=5>by Correy Ananta</font></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1>1. Introduction</h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3>Import data</h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[58]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pylab</span> <span class="k">as</span> <span class="nn">plt</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2>Reading the data set</h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[59]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">filename</span> <span class="o">=</span> <span class="s2">&quot;https://s3-api.us-geo.objectstorage.softlayer.net/cf-courses-data/CognitiveClass/DA0101EN/auto.csv&quot;</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>To better describe our data we can introduce a header, this information is available at: <a href="https://archive.ics.uci.edu/ml/datasets/Automobile">https://archive.ics.uci.edu/ml/datasets/Automobile</a></p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[60]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">headers</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;symboling&quot;</span><span class="p">,</span><span class="s2">&quot;normalized-losses&quot;</span><span class="p">,</span><span class="s2">&quot;make&quot;</span><span class="p">,</span><span class="s2">&quot;fuel-type&quot;</span><span class="p">,</span><span class="s2">&quot;aspiration&quot;</span><span class="p">,</span> <span class="s2">&quot;num-of-doors&quot;</span><span class="p">,</span><span class="s2">&quot;body-style&quot;</span><span class="p">,</span>
         <span class="s2">&quot;drive-wheels&quot;</span><span class="p">,</span><span class="s2">&quot;engine-location&quot;</span><span class="p">,</span><span class="s2">&quot;wheel-base&quot;</span><span class="p">,</span> <span class="s2">&quot;length&quot;</span><span class="p">,</span><span class="s2">&quot;width&quot;</span><span class="p">,</span><span class="s2">&quot;height&quot;</span><span class="p">,</span><span class="s2">&quot;curb-weight&quot;</span><span class="p">,</span><span class="s2">&quot;engine-type&quot;</span><span class="p">,</span>
         <span class="s2">&quot;num-of-cylinders&quot;</span><span class="p">,</span> <span class="s2">&quot;engine-size&quot;</span><span class="p">,</span><span class="s2">&quot;fuel-system&quot;</span><span class="p">,</span><span class="s2">&quot;bore&quot;</span><span class="p">,</span><span class="s2">&quot;stroke&quot;</span><span class="p">,</span><span class="s2">&quot;compression-ratio&quot;</span><span class="p">,</span><span class="s2">&quot;horsepower&quot;</span><span class="p">,</span>
         <span class="s2">&quot;peak-rpm&quot;</span><span class="p">,</span><span class="s2">&quot;city-mpg&quot;</span><span class="p">,</span><span class="s2">&quot;highway-mpg&quot;</span><span class="p">,</span><span class="s2">&quot;price&quot;</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[61]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="n">filename</span><span class="p">,</span> <span class="n">names</span> <span class="o">=</span> <span class="n">headers</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[62]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># To see what the data set looks like, we&#39;ll use the head() method.</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[62]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>fuel-type</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>...</th>
      <th>engine-size</th>
      <th>fuel-system</th>
      <th>bore</th>
      <th>stroke</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>?</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000</td>
      <td>21</td>
      <td>27</td>
      <td>13495</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>?</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000</td>
      <td>21</td>
      <td>27</td>
      <td>16500</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>?</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>...</td>
      <td>152</td>
      <td>mpfi</td>
      <td>2.68</td>
      <td>3.47</td>
      <td>9.0</td>
      <td>154</td>
      <td>5000</td>
      <td>19</td>
      <td>26</td>
      <td>16500</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>...</td>
      <td>109</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>10.0</td>
      <td>102</td>
      <td>5500</td>
      <td>24</td>
      <td>30</td>
      <td>13950</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>...</td>
      <td>136</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.0</td>
      <td>115</td>
      <td>5500</td>
      <td>18</td>
      <td>22</td>
      <td>17450</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 26 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[63]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">df</span><span class="o">.</span><span class="n">columns</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Index([&#39;symboling&#39;, &#39;normalized-losses&#39;, &#39;make&#39;, &#39;fuel-type&#39;, &#39;aspiration&#39;,
       &#39;num-of-doors&#39;, &#39;body-style&#39;, &#39;drive-wheels&#39;, &#39;engine-location&#39;,
       &#39;wheel-base&#39;, &#39;length&#39;, &#39;width&#39;, &#39;height&#39;, &#39;curb-weight&#39;, &#39;engine-type&#39;,
       &#39;num-of-cylinders&#39;, &#39;engine-size&#39;, &#39;fuel-system&#39;, &#39;bore&#39;, &#39;stroke&#39;,
       &#39;compression-ratio&#39;, &#39;horsepower&#39;, &#39;peak-rpm&#39;, &#39;city-mpg&#39;,
       &#39;highway-mpg&#39;, &#39;price&#39;],
      dtype=&#39;object&#39;)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h2>Data Info</h2></p>
<p>
Data has a variety of types.<br>
The main types stored in Pandas dataframes are <b>object</b>, <b>float</b>, <b>int</b>, <b>bool</b> and <b>datetime64</b>. In order to better learn about each attribute, we can use method .info() in Pandas:
</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[64]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>&lt;class &#39;pandas.core.frame.DataFrame&#39;&gt;
RangeIndex: 205 entries, 0 to 204
Data columns (total 26 columns):
 #   Column             Non-Null Count  Dtype  
---  ------             --------------  -----  
 0   symboling          205 non-null    int64  
 1   normalized-losses  205 non-null    object 
 2   make               205 non-null    object 
 3   fuel-type          205 non-null    object 
 4   aspiration         205 non-null    object 
 5   num-of-doors       205 non-null    object 
 6   body-style         205 non-null    object 
 7   drive-wheels       205 non-null    object 
 8   engine-location    205 non-null    object 
 9   wheel-base         205 non-null    float64
 10  length             205 non-null    float64
 11  width              205 non-null    float64
 12  height             205 non-null    float64
 13  curb-weight        205 non-null    int64  
 14  engine-type        205 non-null    object 
 15  num-of-cylinders   205 non-null    object 
 16  engine-size        205 non-null    int64  
 17  fuel-system        205 non-null    object 
 18  bore               205 non-null    object 
 19  stroke             205 non-null    object 
 20  compression-ratio  205 non-null    float64
 21  horsepower         205 non-null    object 
 22  peak-rpm           205 non-null    object 
 23  city-mpg           205 non-null    int64  
 24  highway-mpg        205 non-null    int64  
 25  price              205 non-null    object 
dtypes: float64(5), int64(5), object(16)
memory usage: 41.8+ KB
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h2>Describe</h2>
If we would like to get a statistical summary of each column, such as count, column mean value, column standard deviation, etc. We use method .describe():</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[65]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[65]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>wheel-base</th>
      <th>length</th>
      <th>width</th>
      <th>height</th>
      <th>curb-weight</th>
      <th>engine-size</th>
      <th>compression-ratio</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>205.000000</td>
      <td>205.000000</td>
      <td>205.000000</td>
      <td>205.000000</td>
      <td>205.000000</td>
      <td>205.000000</td>
      <td>205.000000</td>
      <td>205.000000</td>
      <td>205.000000</td>
      <td>205.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>0.834146</td>
      <td>98.756585</td>
      <td>174.049268</td>
      <td>65.907805</td>
      <td>53.724878</td>
      <td>2555.565854</td>
      <td>126.907317</td>
      <td>10.142537</td>
      <td>25.219512</td>
      <td>30.751220</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.245307</td>
      <td>6.021776</td>
      <td>12.337289</td>
      <td>2.145204</td>
      <td>2.443522</td>
      <td>520.680204</td>
      <td>41.642693</td>
      <td>3.972040</td>
      <td>6.542142</td>
      <td>6.886443</td>
    </tr>
    <tr>
      <th>min</th>
      <td>-2.000000</td>
      <td>86.600000</td>
      <td>141.100000</td>
      <td>60.300000</td>
      <td>47.800000</td>
      <td>1488.000000</td>
      <td>61.000000</td>
      <td>7.000000</td>
      <td>13.000000</td>
      <td>16.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.000000</td>
      <td>94.500000</td>
      <td>166.300000</td>
      <td>64.100000</td>
      <td>52.000000</td>
      <td>2145.000000</td>
      <td>97.000000</td>
      <td>8.600000</td>
      <td>19.000000</td>
      <td>25.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.000000</td>
      <td>97.000000</td>
      <td>173.200000</td>
      <td>65.500000</td>
      <td>54.100000</td>
      <td>2414.000000</td>
      <td>120.000000</td>
      <td>9.000000</td>
      <td>24.000000</td>
      <td>30.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2.000000</td>
      <td>102.400000</td>
      <td>183.100000</td>
      <td>66.900000</td>
      <td>55.500000</td>
      <td>2935.000000</td>
      <td>141.000000</td>
      <td>9.400000</td>
      <td>30.000000</td>
      <td>34.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3.000000</td>
      <td>120.900000</td>
      <td>208.100000</td>
      <td>72.300000</td>
      <td>59.800000</td>
      <td>4066.000000</td>
      <td>326.000000</td>
      <td>23.000000</td>
      <td>49.000000</td>
      <td>54.000000</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1>2. Data Wrangling</h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2>Table of content</h2><div class="alert alert-block alert-info" style="margin-top: 20px">
<ul>
    <li><a href="#identify_handle_missing_values">Identify and handle missing values</a>
        <ul>
            <li><a href="#identify_missing_values">Identify missing values</a></li>
            <li><a href="#deal_missing_values">Deal with missing values</a></li>
            <li><a href="#correct_data_format">Correct data format</a></li>
        </ul>
    </li>
    <li><a href="#data_standardization">Data standardization</a></li>
    <li><a href="#data_normalization">Data Normalization (centering/scaling)</a></li>
    <li><a href="#binning">Binning</a></li>
    <li><a href="#indicator">Indicator variable</a></li>
</ul>

Estimated Time Needed: <strong>30 min</strong>
</div><hr>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2>What is the purpose of Data Wrangling?</h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Data Wrangling is the process of converting data from the initial format to a format that may be better for analysis.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[66]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">20</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[66]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>fuel-type</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>...</th>
      <th>engine-size</th>
      <th>fuel-system</th>
      <th>bore</th>
      <th>stroke</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>?</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000</td>
      <td>21</td>
      <td>27</td>
      <td>13495</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>?</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000</td>
      <td>21</td>
      <td>27</td>
      <td>16500</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>?</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>...</td>
      <td>152</td>
      <td>mpfi</td>
      <td>2.68</td>
      <td>3.47</td>
      <td>9.0</td>
      <td>154</td>
      <td>5000</td>
      <td>19</td>
      <td>26</td>
      <td>16500</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>...</td>
      <td>109</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>10.0</td>
      <td>102</td>
      <td>5500</td>
      <td>24</td>
      <td>30</td>
      <td>13950</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>...</td>
      <td>136</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.0</td>
      <td>115</td>
      <td>5500</td>
      <td>18</td>
      <td>22</td>
      <td>17450</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2</td>
      <td>?</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>...</td>
      <td>136</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.5</td>
      <td>110</td>
      <td>5500</td>
      <td>19</td>
      <td>25</td>
      <td>15250</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1</td>
      <td>158</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>105.8</td>
      <td>...</td>
      <td>136</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.5</td>
      <td>110</td>
      <td>5500</td>
      <td>19</td>
      <td>25</td>
      <td>17710</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1</td>
      <td>?</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>wagon</td>
      <td>fwd</td>
      <td>front</td>
      <td>105.8</td>
      <td>...</td>
      <td>136</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.5</td>
      <td>110</td>
      <td>5500</td>
      <td>19</td>
      <td>25</td>
      <td>18920</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1</td>
      <td>158</td>
      <td>audi</td>
      <td>gas</td>
      <td>turbo</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>105.8</td>
      <td>...</td>
      <td>131</td>
      <td>mpfi</td>
      <td>3.13</td>
      <td>3.40</td>
      <td>8.3</td>
      <td>140</td>
      <td>5500</td>
      <td>17</td>
      <td>20</td>
      <td>23875</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0</td>
      <td>?</td>
      <td>audi</td>
      <td>gas</td>
      <td>turbo</td>
      <td>two</td>
      <td>hatchback</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.5</td>
      <td>...</td>
      <td>131</td>
      <td>mpfi</td>
      <td>3.13</td>
      <td>3.40</td>
      <td>7.0</td>
      <td>160</td>
      <td>5500</td>
      <td>16</td>
      <td>22</td>
      <td>?</td>
    </tr>
    <tr>
      <th>10</th>
      <td>2</td>
      <td>192</td>
      <td>bmw</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>sedan</td>
      <td>rwd</td>
      <td>front</td>
      <td>101.2</td>
      <td>...</td>
      <td>108</td>
      <td>mpfi</td>
      <td>3.50</td>
      <td>2.80</td>
      <td>8.8</td>
      <td>101</td>
      <td>5800</td>
      <td>23</td>
      <td>29</td>
      <td>16430</td>
    </tr>
    <tr>
      <th>11</th>
      <td>0</td>
      <td>192</td>
      <td>bmw</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>rwd</td>
      <td>front</td>
      <td>101.2</td>
      <td>...</td>
      <td>108</td>
      <td>mpfi</td>
      <td>3.50</td>
      <td>2.80</td>
      <td>8.8</td>
      <td>101</td>
      <td>5800</td>
      <td>23</td>
      <td>29</td>
      <td>16925</td>
    </tr>
    <tr>
      <th>12</th>
      <td>0</td>
      <td>188</td>
      <td>bmw</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>sedan</td>
      <td>rwd</td>
      <td>front</td>
      <td>101.2</td>
      <td>...</td>
      <td>164</td>
      <td>mpfi</td>
      <td>3.31</td>
      <td>3.19</td>
      <td>9.0</td>
      <td>121</td>
      <td>4250</td>
      <td>21</td>
      <td>28</td>
      <td>20970</td>
    </tr>
    <tr>
      <th>13</th>
      <td>0</td>
      <td>188</td>
      <td>bmw</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>rwd</td>
      <td>front</td>
      <td>101.2</td>
      <td>...</td>
      <td>164</td>
      <td>mpfi</td>
      <td>3.31</td>
      <td>3.19</td>
      <td>9.0</td>
      <td>121</td>
      <td>4250</td>
      <td>21</td>
      <td>28</td>
      <td>21105</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1</td>
      <td>?</td>
      <td>bmw</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>rwd</td>
      <td>front</td>
      <td>103.5</td>
      <td>...</td>
      <td>164</td>
      <td>mpfi</td>
      <td>3.31</td>
      <td>3.19</td>
      <td>9.0</td>
      <td>121</td>
      <td>4250</td>
      <td>20</td>
      <td>25</td>
      <td>24565</td>
    </tr>
    <tr>
      <th>15</th>
      <td>0</td>
      <td>?</td>
      <td>bmw</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>rwd</td>
      <td>front</td>
      <td>103.5</td>
      <td>...</td>
      <td>209</td>
      <td>mpfi</td>
      <td>3.62</td>
      <td>3.39</td>
      <td>8.0</td>
      <td>182</td>
      <td>5400</td>
      <td>16</td>
      <td>22</td>
      <td>30760</td>
    </tr>
    <tr>
      <th>16</th>
      <td>0</td>
      <td>?</td>
      <td>bmw</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>sedan</td>
      <td>rwd</td>
      <td>front</td>
      <td>103.5</td>
      <td>...</td>
      <td>209</td>
      <td>mpfi</td>
      <td>3.62</td>
      <td>3.39</td>
      <td>8.0</td>
      <td>182</td>
      <td>5400</td>
      <td>16</td>
      <td>22</td>
      <td>41315</td>
    </tr>
    <tr>
      <th>17</th>
      <td>0</td>
      <td>?</td>
      <td>bmw</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>rwd</td>
      <td>front</td>
      <td>110.0</td>
      <td>...</td>
      <td>209</td>
      <td>mpfi</td>
      <td>3.62</td>
      <td>3.39</td>
      <td>8.0</td>
      <td>182</td>
      <td>5400</td>
      <td>15</td>
      <td>20</td>
      <td>36880</td>
    </tr>
    <tr>
      <th>18</th>
      <td>2</td>
      <td>121</td>
      <td>chevrolet</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>fwd</td>
      <td>front</td>
      <td>88.4</td>
      <td>...</td>
      <td>61</td>
      <td>2bbl</td>
      <td>2.91</td>
      <td>3.03</td>
      <td>9.5</td>
      <td>48</td>
      <td>5100</td>
      <td>47</td>
      <td>53</td>
      <td>5151</td>
    </tr>
    <tr>
      <th>19</th>
      <td>1</td>
      <td>98</td>
      <td>chevrolet</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>fwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>...</td>
      <td>90</td>
      <td>2bbl</td>
      <td>3.03</td>
      <td>3.11</td>
      <td>9.6</td>
      <td>70</td>
      <td>5400</td>
      <td>38</td>
      <td>43</td>
      <td>6295</td>
    </tr>
  </tbody>
</table>
<p>20 rows × 26 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>As we can see, several question marks appeared in the dataframe; those are missing values which may hinder our further analysis.</p>
<div>So, how do we identify all those missing values and deal with them?</div><p><b>How to work with missing data?</b></p>
<p>Steps for working with missing data:</p>
<ol>
    <li>identify missing data</li>
    <li>deal with missing data</li>
    <li>correct data format</li>
</ol>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="identify_handle_missing_values">2.1 Identify and handle missing values</h2><p><h3 id="identify_missing_values">A. Identify missing values</h3></p>
<p><h4>Convert "?" to NaN</h4>
In the our dataset, missing data comes with the question mark "?".
We replace "?" with NaN (Not a Number), which is Python's default missing value marker, for reasons of computational speed and convenience. Here we use the function: 
 <pre>.replace(A, B, inplace = True) </pre>
to replace A by B</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[67]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="c1"># replace &quot;?&quot; to NaN</span>
<span class="n">df</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s2">&quot;?&quot;</span><span class="p">,</span> <span class="n">np</span><span class="o">.</span><span class="n">nan</span><span class="p">,</span> <span class="n">inplace</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">5</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[67]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>fuel-type</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>...</th>
      <th>engine-size</th>
      <th>fuel-system</th>
      <th>bore</th>
      <th>stroke</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>NaN</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000</td>
      <td>21</td>
      <td>27</td>
      <td>13495</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>NaN</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000</td>
      <td>21</td>
      <td>27</td>
      <td>16500</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>NaN</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>...</td>
      <td>152</td>
      <td>mpfi</td>
      <td>2.68</td>
      <td>3.47</td>
      <td>9.0</td>
      <td>154</td>
      <td>5000</td>
      <td>19</td>
      <td>26</td>
      <td>16500</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>...</td>
      <td>109</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>10.0</td>
      <td>102</td>
      <td>5500</td>
      <td>24</td>
      <td>30</td>
      <td>13950</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>...</td>
      <td>136</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.0</td>
      <td>115</td>
      <td>5500</td>
      <td>18</td>
      <td>22</td>
      <td>17450</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 26 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Evaluating for Missing Data</h4><p>The missing values are converted to Python's default. We use Python's built-in functions to identify these missing values. There are two methods to detect missing data:</p>
<p><ol>
    <li><b>.isnull()</b></li>
    <li><b>.notnull()</b></li>
</ol>
The output is a boolean value indicating whether the value that is passed into the argument is in fact missing data.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[68]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">missing_data</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span>
<span class="n">missing_data</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">5</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[68]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>fuel-type</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>...</th>
      <th>engine-size</th>
      <th>fuel-system</th>
      <th>bore</th>
      <th>stroke</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>False</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>False</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 26 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>"True" stands for missing value, while "False" stands for not missing value.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h4>Count missing values in each column</h4></p>
<p>
Using a for loop in Python, we can quickly figure out the number of missing values in each column. As mentioned above, "True" represents a missing value, "False"  means the value is present in the dataset.  In the body of the for loop the method  ".value_counts()"  counts the number of "True" values. 
</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[69]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">for</span> <span class="n">column</span> <span class="ow">in</span> <span class="n">missing_data</span><span class="o">.</span><span class="n">columns</span><span class="o">.</span><span class="n">values</span><span class="o">.</span><span class="n">tolist</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">column</span><span class="p">)</span>
    <span class="nb">print</span> <span class="p">(</span><span class="n">missing_data</span><span class="p">[</span><span class="n">column</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">())</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;&quot;</span><span class="p">)</span>    
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>symboling
False    205
Name: symboling, dtype: int64

normalized-losses
False    164
True      41
Name: normalized-losses, dtype: int64

make
False    205
Name: make, dtype: int64

fuel-type
False    205
Name: fuel-type, dtype: int64

aspiration
False    205
Name: aspiration, dtype: int64

num-of-doors
False    203
True       2
Name: num-of-doors, dtype: int64

body-style
False    205
Name: body-style, dtype: int64

drive-wheels
False    205
Name: drive-wheels, dtype: int64

engine-location
False    205
Name: engine-location, dtype: int64

wheel-base
False    205
Name: wheel-base, dtype: int64

length
False    205
Name: length, dtype: int64

width
False    205
Name: width, dtype: int64

height
False    205
Name: height, dtype: int64

curb-weight
False    205
Name: curb-weight, dtype: int64

engine-type
False    205
Name: engine-type, dtype: int64

num-of-cylinders
False    205
Name: num-of-cylinders, dtype: int64

engine-size
False    205
Name: engine-size, dtype: int64

fuel-system
False    205
Name: fuel-system, dtype: int64

bore
False    201
True       4
Name: bore, dtype: int64

stroke
False    201
True       4
Name: stroke, dtype: int64

compression-ratio
False    205
Name: compression-ratio, dtype: int64

horsepower
False    203
True       2
Name: horsepower, dtype: int64

peak-rpm
False    203
True       2
Name: peak-rpm, dtype: int64

city-mpg
False    205
Name: city-mpg, dtype: int64

highway-mpg
False    205
Name: highway-mpg, dtype: int64

price
False    201
True       4
Name: price, dtype: int64

</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[70]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># other method to count of missing value</span>
<span class="n">count_nan</span> <span class="o">=</span> <span class="nb">len</span><span class="p">(</span><span class="n">df</span><span class="p">)</span> <span class="o">-</span> <span class="n">df</span><span class="o">.</span><span class="n">count</span><span class="p">()</span>
<span class="n">count_nan</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[70]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>symboling             0
normalized-losses    41
make                  0
fuel-type             0
aspiration            0
num-of-doors          2
body-style            0
drive-wheels          0
engine-location       0
wheel-base            0
length                0
width                 0
height                0
curb-weight           0
engine-type           0
num-of-cylinders      0
engine-size           0
fuel-system           0
bore                  4
stroke                4
compression-ratio     0
horsepower            2
peak-rpm              2
city-mpg              0
highway-mpg           0
price                 4
dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Based on the summary above, each column has 205 rows of data, seven columns containing missing data:</p>
<ol>
    <li>"normalized-losses": 41 missing data</li>
    <li>"num-of-doors": 2 missing data</li>
    <li>"bore": 4 missing data</li>
    <li>"stroke" : 4 missing data</li>
    <li>"horsepower": 2 missing data</li>
    <li>"peak-rpm": 2 missing data</li>
    <li>"price": 4 missing data</li>
</ol>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h3 id="deal_missing_values">B. Deal with missing data</h3>
<b>How to deal with missing data?</b></p>
<ol>
    <li>drop data<br>
        a. drop the whole row<br>
        b. drop the whole column
    </li>
    <li>replace data<br>
        a. replace it by mean<br>
        b. replace it by frequency<br>
        c. replace it based on other functions
    </li>
</ol>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Whole columns should be dropped only if most entries in the column are empty. In our dataset, none of the columns are empty enough to drop entirely.
We have some freedom in choosing which method to replace data; however, some methods may seem more reasonable than others. We will apply each method to many different columns:</p>
<p><b>Replace by mean:</b></p>
<ul>
    <li>"normalized-losses": 41 missing data, replace them with mean</li>
    <li>"stroke": 4 missing data, replace them with mean</li>
    <li>"bore": 4 missing data, replace them with mean</li>
    <li>"horsepower": 2 missing data, replace them with mean</li>
    <li>"peak-rpm": 2 missing data, replace them with mean</li>
</ul><p><b>Replace by frequency:</b></p>
<ul>
    <li>"num-of-doors": 2 missing data, replace them with "four". 
        <ul>
            <li>Reason: 84% sedans is four doors. Since four doors is most frequent, it is most likely to occur</li>
        </ul>
    </li>
</ul><p><b>Drop the whole row:</b></p>
<ul>
    <li>"price": 4 missing data, simply delete the whole row
        <ul>
            <li>Reason: price is what we want to predict. Any data entry without price data cannot be used for prediction; therefore any row now without price data is not useful to us</li>
        </ul>
    </li>
</ul>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Calculate the average of the column </h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[71]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">avg_norm_loss</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s2">&quot;normalized-losses&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;float&quot;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Average of normalized-losses:&quot;</span><span class="p">,</span> <span class="n">avg_norm_loss</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average of normalized-losses: 122.0
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Replace "NaN" by mean value in "normalized-losses" column</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[72]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;normalized-losses&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">nan</span><span class="p">,</span> <span class="n">avg_norm_loss</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Calculate the mean value for 'bore' column</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[73]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">avg_bore</span><span class="o">=</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;bore&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;float&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Average of bore:&quot;</span><span class="p">,</span> <span class="n">avg_bore</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average of bore: 3.3297512437810943
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Replace NaN by mean value</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[74]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;bore&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">nan</span><span class="p">,</span> <span class="n">avg_bore</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><b>According to the example above, replace NaN in "stroke" column by mean.</b>
&lt;/div&gt;</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[75]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">avg_stroke</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s2">&quot;stroke&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;float&quot;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">df</span><span class="p">[</span><span class="s2">&quot;stroke&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">nan</span><span class="p">,</span> <span class="n">avg_stroke</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Calculate the mean value for the  'horsepower' column:</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[76]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">avg_horsepower</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;horsepower&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;float&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Average horsepower:&quot;</span><span class="p">,</span> <span class="n">avg_horsepower</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average horsepower: 104.25615763546799
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Replace "NaN" by mean value:</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[77]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;horsepower&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">nan</span><span class="p">,</span> <span class="n">avg_horsepower</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Calculate the mean value for 'peak-rpm' column:</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[78]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">avg_peakrpm</span><span class="o">=</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;peak-rpm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;float&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Average peak rpm:&quot;</span><span class="p">,</span> <span class="n">avg_peakrpm</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Average peak rpm: 5125.369458128079
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Replace NaN by mean value:</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[79]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;peak-rpm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">nan</span><span class="p">,</span> <span class="n">avg_peakrpm</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>To see which values are present in a particular column, we can use the ".value_counts()" method:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[80]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;num-of-doors&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[80]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>four    114
two      89
Name: num-of-doors, dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>We can see that four doors are the most common type. We can also use the ".idxmax()" method to calculate for us the most common type automatically:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[81]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;num-of-doors&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">idxmax</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[81]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&#39;four&#39;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The replacement procedure is very similar to what we have seen previously</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[82]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#replace the missing &#39;num-of-doors&#39; values by the most frequent </span>
<span class="n">df</span><span class="p">[</span><span class="s2">&quot;num-of-doors&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">nan</span><span class="p">,</span> <span class="s2">&quot;four&quot;</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Finally, let's drop all rows that do not have price data:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[83]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># simply drop whole row with NaN in &quot;price&quot; column</span>
<span class="n">df</span><span class="o">.</span><span class="n">dropna</span><span class="p">(</span><span class="n">subset</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;price&quot;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>

<span class="c1"># reset index, because we droped two rows</span>
<span class="n">df</span><span class="o">.</span><span class="n">reset_index</span><span class="p">(</span><span class="n">drop</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[84]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[84]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>fuel-type</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>...</th>
      <th>engine-size</th>
      <th>fuel-system</th>
      <th>bore</th>
      <th>stroke</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000</td>
      <td>21</td>
      <td>27</td>
      <td>13495</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000</td>
      <td>21</td>
      <td>27</td>
      <td>16500</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>...</td>
      <td>152</td>
      <td>mpfi</td>
      <td>2.68</td>
      <td>3.47</td>
      <td>9.0</td>
      <td>154</td>
      <td>5000</td>
      <td>19</td>
      <td>26</td>
      <td>16500</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>...</td>
      <td>109</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>10.0</td>
      <td>102</td>
      <td>5500</td>
      <td>24</td>
      <td>30</td>
      <td>13950</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>...</td>
      <td>136</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.0</td>
      <td>115</td>
      <td>5500</td>
      <td>18</td>
      <td>22</td>
      <td>17450</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 26 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><b>Good!</b> Now, we obtain the dataset with no missing values.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h3 id="correct_data_format">C. Correct data format</h3>
<b>We are almost there!</b></p>
<p>The last step in data cleaning is checking and making sure that all data is in the correct format (int, float, text or other).</p><p>In Pandas, we use</p>
<p><b>.dtype()</b> to check the data type</p>
<p><b>.astype()</b> to change the data type</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Lets list the data types for each column</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[85]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">dtypes</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[85]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>symboling              int64
normalized-losses     object
make                  object
fuel-type             object
aspiration            object
num-of-doors          object
body-style            object
drive-wheels          object
engine-location       object
wheel-base           float64
length               float64
width                float64
height               float64
curb-weight            int64
engine-type           object
num-of-cylinders      object
engine-size            int64
fuel-system           object
bore                  object
stroke                object
compression-ratio    float64
horsepower            object
peak-rpm              object
city-mpg               int64
highway-mpg            int64
price                 object
dtype: object</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>As we can see above, some columns are not of the correct data type. Numerical variables should have type 'float' or 'int', and variables with strings such as categories should have type 'object'. For example, 'bore' and 'stroke' variables are numerical values that describe the engines, so we should expect them to be of the type 'float' or 'int'; however, they are shown as type 'object'. We have to convert data types into a proper format for each column using the "astype()" method.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Convert data types to proper format</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[86]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[[</span><span class="s2">&quot;bore&quot;</span><span class="p">,</span> <span class="s2">&quot;stroke&quot;</span><span class="p">]]</span> <span class="o">=</span> <span class="n">df</span><span class="p">[[</span><span class="s2">&quot;bore&quot;</span><span class="p">,</span> <span class="s2">&quot;stroke&quot;</span><span class="p">]]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;float&quot;</span><span class="p">)</span>
<span class="n">df</span><span class="p">[[</span><span class="s2">&quot;normalized-losses&quot;</span><span class="p">]]</span> <span class="o">=</span> <span class="n">df</span><span class="p">[[</span><span class="s2">&quot;normalized-losses&quot;</span><span class="p">]]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;int&quot;</span><span class="p">)</span>
<span class="n">df</span><span class="p">[[</span><span class="s2">&quot;price&quot;</span><span class="p">]]</span> <span class="o">=</span> <span class="n">df</span><span class="p">[[</span><span class="s2">&quot;price&quot;</span><span class="p">]]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;float&quot;</span><span class="p">)</span>
<span class="n">df</span><span class="p">[[</span><span class="s2">&quot;peak-rpm&quot;</span><span class="p">]]</span> <span class="o">=</span> <span class="n">df</span><span class="p">[[</span><span class="s2">&quot;peak-rpm&quot;</span><span class="p">]]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s2">&quot;float&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4>Let us list the columns after the conversion</h4>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[87]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">dtypes</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[87]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>symboling              int64
normalized-losses      int32
make                  object
fuel-type             object
aspiration            object
num-of-doors          object
body-style            object
drive-wheels          object
engine-location       object
wheel-base           float64
length               float64
width                float64
height               float64
curb-weight            int64
engine-type           object
num-of-cylinders      object
engine-size            int64
fuel-system           object
bore                 float64
stroke               float64
compression-ratio    float64
horsepower            object
peak-rpm             float64
city-mpg               int64
highway-mpg            int64
price                float64
dtype: object</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h2 id="data_standardization">2.2 Data Standardization</h2></p>
<p>
Data is usually collected from different agencies with different formats.
(Data Standardization is also a term for a particular type of data normalization, where we subtract the mean and divide by the standard deviation)
</p><p><b>What is Standardization?</b></p>
<p>Standardization is the process of transforming data into a common format which allows the researcher to make the meaningful comparison.
</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[88]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[88]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>fuel-type</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>...</th>
      <th>engine-size</th>
      <th>fuel-system</th>
      <th>bore</th>
      <th>stroke</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000.0</td>
      <td>21</td>
      <td>27</td>
      <td>13495.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>130</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000.0</td>
      <td>21</td>
      <td>27</td>
      <td>16500.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>...</td>
      <td>152</td>
      <td>mpfi</td>
      <td>2.68</td>
      <td>3.47</td>
      <td>9.0</td>
      <td>154</td>
      <td>5000.0</td>
      <td>19</td>
      <td>26</td>
      <td>16500.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>...</td>
      <td>109</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>10.0</td>
      <td>102</td>
      <td>5500.0</td>
      <td>24</td>
      <td>30</td>
      <td>13950.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>...</td>
      <td>136</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.0</td>
      <td>115</td>
      <td>5500.0</td>
      <td>18</td>
      <td>22</td>
      <td>17450.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 26 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Convert mpg to L/100km by mathematical operation (235 divided by mpg)</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[89]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;city-L/100km&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="mi">235</span><span class="o">/</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;city-mpg&quot;</span><span class="p">]</span>

<span class="c1"># check your transformed data </span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[89]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>fuel-type</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>...</th>
      <th>fuel-system</th>
      <th>bore</th>
      <th>stroke</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
      <th>city-L/100km</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000.0</td>
      <td>21</td>
      <td>27</td>
      <td>13495.0</td>
      <td>11.190476</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000.0</td>
      <td>21</td>
      <td>27</td>
      <td>16500.0</td>
      <td>11.190476</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>...</td>
      <td>mpfi</td>
      <td>2.68</td>
      <td>3.47</td>
      <td>9.0</td>
      <td>154</td>
      <td>5000.0</td>
      <td>19</td>
      <td>26</td>
      <td>16500.0</td>
      <td>12.368421</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>...</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>10.0</td>
      <td>102</td>
      <td>5500.0</td>
      <td>24</td>
      <td>30</td>
      <td>13950.0</td>
      <td>9.791667</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>...</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.0</td>
      <td>115</td>
      <td>5500.0</td>
      <td>18</td>
      <td>22</td>
      <td>17450.0</td>
      <td>13.055556</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 27 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Transform mpg to L/100km in the column of "highway-mpg", and change the name of column to "highway-L/100km".</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[90]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;highway-mpg&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="mi">235</span><span class="o">/</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;highway-mpg&quot;</span><span class="p">]</span> 
<span class="n">df</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span> <span class="p">{</span><span class="s2">&quot;highway-L/100km&quot;</span><span class="p">:</span><span class="s2">&quot;highway-L/100km&quot;</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[90]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>fuel-type</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>...</th>
      <th>fuel-system</th>
      <th>bore</th>
      <th>stroke</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
      <th>city-L/100km</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000.0</td>
      <td>21</td>
      <td>8.703704</td>
      <td>13495.0</td>
      <td>11.190476</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>...</td>
      <td>mpfi</td>
      <td>3.47</td>
      <td>2.68</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000.0</td>
      <td>21</td>
      <td>8.703704</td>
      <td>16500.0</td>
      <td>11.190476</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>gas</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>...</td>
      <td>mpfi</td>
      <td>2.68</td>
      <td>3.47</td>
      <td>9.0</td>
      <td>154</td>
      <td>5000.0</td>
      <td>19</td>
      <td>9.038462</td>
      <td>16500.0</td>
      <td>12.368421</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>...</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>10.0</td>
      <td>102</td>
      <td>5500.0</td>
      <td>24</td>
      <td>7.833333</td>
      <td>13950.0</td>
      <td>9.791667</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>gas</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>...</td>
      <td>mpfi</td>
      <td>3.19</td>
      <td>3.40</td>
      <td>8.0</td>
      <td>115</td>
      <td>5500.0</td>
      <td>18</td>
      <td>10.681818</td>
      <td>17450.0</td>
      <td>13.055556</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 27 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="data_normalization">2.3 Data Normalization</h2><p><b>Why normalization?</b></p>
<p>Normalization is the process of transforming values of several variables into a similar range. Typical normalizations include scaling the variable so the variable average is 0, scaling the variable so the variance is 1, or scaling variable so the variable values range from 0 to 1
</p><p><b>Example</b></p>
<p>To demonstrate normalization, let's say we want to scale the columns "length", "width" and "height" </p>
<p><b>Target:</b>would like to Normalize those variables so their value ranges from 0 to 1.</p>
<p><b>Approach:</b> replace original value by (original value)/(maximum value)</p><p><a href="https://www.wallstreetmojo.com/normalization-formula/"><img src="https://www.wallstreetmojo.com/wp-content/uploads/2019/04/Normalization-Formula.jpg" width=300, align="center"></a></p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[91]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># replace (original value) by (original value)/(maximum value)</span>
<span class="n">df</span><span class="p">[</span><span class="s1">&#39;length&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;length&#39;</span><span class="p">]</span><span class="o">/</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;length&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">max</span><span class="p">()</span>
<span class="n">df</span><span class="p">[</span><span class="s1">&#39;width&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;width&#39;</span><span class="p">]</span><span class="o">/</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;width&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">max</span><span class="p">()</span>
<span class="n">df</span><span class="p">[</span><span class="s2">&quot;height&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s2">&quot;height&quot;</span><span class="p">]</span><span class="o">/</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;height&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">max</span><span class="p">()</span>
<span class="n">df</span><span class="p">[[</span><span class="s2">&quot;length&quot;</span><span class="p">,</span><span class="s2">&quot;width&quot;</span><span class="p">,</span><span class="s2">&quot;height&quot;</span><span class="p">]]</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[91]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>length</th>
      <th>width</th>
      <th>height</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.811148</td>
      <td>0.890278</td>
      <td>0.816054</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.811148</td>
      <td>0.890278</td>
      <td>0.816054</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.822681</td>
      <td>0.909722</td>
      <td>0.876254</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.848630</td>
      <td>0.919444</td>
      <td>0.908027</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.848630</td>
      <td>0.922222</td>
      <td>0.908027</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Here we can see, we've normalized "length", "width" and "height" in the range of [0,1].</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h2 id="binning">2.4 Binning</h2>
<b>Why binning?</b></p>
<p>
    Binning is a process of transforming continuous numerical variables into discrete categorical 'bins', for grouped analysis.
</p><p><b>Example: </b></p>
<p>In our dataset, "horsepower" is a real valued variable ranging from 48 to 288, it has 57 unique values. What if we only care about the price difference between cars with high horsepower, medium horsepower, and little horsepower (3 types)? Can we rearrange them into three ‘bins' to simplify analysis? </p><p>We will use the Pandas method 'cut' to segment the 'horsepower' column into 3 bins </p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[92]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;horsepower&quot;</span><span class="p">]</span><span class="o">=</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;horsepower&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">int</span><span class="p">,</span> <span class="n">copy</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Lets plot the histogram of horspower, to see what the distribution of horsepower looks like.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[93]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">%</span><span class="k">matplotlib</span> inline
<span class="kn">import</span> <span class="nn">matplotlib</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">from</span> <span class="nn">matplotlib</span> <span class="kn">import</span> <span class="n">pyplot</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">hist</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;horsepower&quot;</span><span class="p">])</span>

<span class="c1"># set x/y labels and plot title</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;horsepower&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;count&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;horsepower bins&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[93]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 1.0, &#39;horsepower bins&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>We would like 3 bins of equal size bandwidth so we use numpy's <code>linspace(start_value, end_value, numbers_generated</code> function.</p>
<p>Since we want to include the minimum value of horsepower we want to set start_value=min(df["horsepower"]).</p>
<p>Since we want to include the maximum value of horsepower we want to set end_value=max(df["horsepower"]).</p>
<p>Since we are building 3 bins of equal length, there should be 4 dividers, so numbers_generated=4.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>We build a bin array, with a minimum value to a maximum value, with bandwidth calculated above. The bins will be values used to determine when one bin ends and another begins.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[94]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">bins</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="nb">min</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;horsepower&quot;</span><span class="p">]),</span> <span class="nb">max</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;horsepower&quot;</span><span class="p">]),</span> <span class="mi">4</span><span class="p">)</span>
<span class="n">bins</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[94]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>array([ 48.        , 119.33333333, 190.66666667, 262.        ])</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>We set group  names:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[95]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">group_names</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Low&#39;</span><span class="p">,</span> <span class="s1">&#39;Medium&#39;</span><span class="p">,</span> <span class="s1">&#39;High&#39;</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>We apply the function "cut" the determine what each value of "df['horsepower']" belongs to.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[96]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;horsepower-binned&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">cut</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;horsepower&#39;</span><span class="p">],</span> <span class="n">bins</span><span class="p">,</span> <span class="n">labels</span><span class="o">=</span><span class="n">group_names</span><span class="p">,</span> <span class="n">include_lowest</span><span class="o">=</span><span class="kc">True</span> <span class="p">)</span>
<span class="n">df</span><span class="p">[[</span><span class="s1">&#39;horsepower&#39;</span><span class="p">,</span><span class="s1">&#39;horsepower-binned&#39;</span><span class="p">]]</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">20</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[96]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>horsepower</th>
      <th>horsepower-binned</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>111</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>1</th>
      <td>111</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>2</th>
      <td>154</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>3</th>
      <td>102</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>4</th>
      <td>115</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>5</th>
      <td>110</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>6</th>
      <td>110</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>7</th>
      <td>110</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>8</th>
      <td>140</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>9</th>
      <td>101</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>10</th>
      <td>101</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>11</th>
      <td>121</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>12</th>
      <td>121</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>13</th>
      <td>121</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>14</th>
      <td>182</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>15</th>
      <td>182</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>16</th>
      <td>182</td>
      <td>Medium</td>
    </tr>
    <tr>
      <th>17</th>
      <td>48</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>18</th>
      <td>70</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>19</th>
      <td>70</td>
      <td>Low</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Lets see the number of vehicles in each bin.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[97]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;horsepower-binned&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[97]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Low       153
Medium     43
High        5
Name: horsepower-binned, dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Lets plot the distribution of each bin.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[98]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">%</span><span class="k">matplotlib</span> inline
<span class="kn">import</span> <span class="nn">matplotlib</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">from</span> <span class="nn">matplotlib</span> <span class="kn">import</span> <span class="n">pyplot</span>
<span class="n">pyplot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">group_names</span><span class="p">,</span> <span class="n">df</span><span class="p">[</span><span class="s2">&quot;horsepower-binned&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">())</span>

<span class="c1"># set x/y labels and plot title</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;horsepower&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;count&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;horsepower bins&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[98]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 1.0, &#39;horsepower bins&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>
    Check the dataframe above carefully, you will find the last column provides the bins for "horsepower" with 3 categories ("Low","Medium" and "High"). 
</p>
<p>
    We successfully narrow the intervals from 57 to 3!
</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h3>Bins visualization</h3>
Normally, a histogram is used to visualize the distribution of bins we created above.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[99]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">%</span><span class="k">matplotlib</span> inline
<span class="kn">import</span> <span class="nn">matplotlib</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">from</span> <span class="nn">matplotlib</span> <span class="kn">import</span> <span class="n">pyplot</span>

<span class="n">a</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">)</span>

<span class="c1"># draw historgram of attribute &quot;horsepower&quot; with bins = 3</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">hist</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;horsepower&quot;</span><span class="p">],</span> <span class="n">bins</span> <span class="o">=</span> <span class="mi">3</span><span class="p">)</span>

<span class="c1"># set x/y labels and plot title</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;horsepower&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;count&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pyplot</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;horsepower bins&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[99]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 1.0, &#39;horsepower bins&#39;)</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The plot above shows the binning result for attribute "horsepower".</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h2 id="indicator">2.5 Indicator variable (or dummy variable)</h2>
<b>What is an indicator variable?</b></p>
<p>
    An indicator variable (or dummy variable) is a numerical variable used to label categories. They are called 'dummies' because the numbers themselves don't have inherent meaning. 
</p><p><b>Why we use indicator variables?</b></p>
<p>
    So we can use categorical variables for regression analysis in the later modules.
</p>
<b>Example</b>
<p>
    We see the column "fuel-type" has two unique values, "gas" or "diesel". Regression doesn't understand words, only numbers. To use this attribute in regression analysis, we convert "fuel-type" into indicator variables.
</p><p>
    We will use the panda's method 'get_dummies' to assign numerical values to different categories of fuel type. 
</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[100]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">columns</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[100]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Index([&#39;symboling&#39;, &#39;normalized-losses&#39;, &#39;make&#39;, &#39;fuel-type&#39;, &#39;aspiration&#39;,
       &#39;num-of-doors&#39;, &#39;body-style&#39;, &#39;drive-wheels&#39;, &#39;engine-location&#39;,
       &#39;wheel-base&#39;, &#39;length&#39;, &#39;width&#39;, &#39;height&#39;, &#39;curb-weight&#39;, &#39;engine-type&#39;,
       &#39;num-of-cylinders&#39;, &#39;engine-size&#39;, &#39;fuel-system&#39;, &#39;bore&#39;, &#39;stroke&#39;,
       &#39;compression-ratio&#39;, &#39;horsepower&#39;, &#39;peak-rpm&#39;, &#39;city-mpg&#39;,
       &#39;highway-mpg&#39;, &#39;price&#39;, &#39;city-L/100km&#39;, &#39;horsepower-binned&#39;],
      dtype=&#39;object&#39;)</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>get indicator variables and assign it to data frame "dummy_variable_1"</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[101]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dummy_variable_1</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">get_dummies</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;fuel-type&quot;</span><span class="p">])</span>
<span class="n">dummy_variable_1</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">20</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[101]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>diesel</th>
      <th>gas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>10</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>12</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>13</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>14</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>16</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>17</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>18</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>19</th>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>change column names for clarity</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[102]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dummy_variable_1</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;gas&#39;</span><span class="p">:</span><span class="s1">&#39;fuel-type-gas&#39;</span><span class="p">,</span> <span class="s1">&#39;diesel&#39;</span><span class="p">:</span><span class="s1">&#39;fuel-type-diesel&#39;</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">dummy_variable_1</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">20</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[102]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>fuel-type-diesel</th>
      <th>fuel-type-gas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>10</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>12</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>13</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>14</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>15</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>16</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>17</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>18</th>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>19</th>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>We now have the value 0 to represent "gas" and 1 to represent "diesel" in the column "fuel-type". We will now insert this column back into our original dataset.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[103]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># merge data frame &quot;df&quot; and &quot;dummy_variable_1&quot; </span>
<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">df</span><span class="p">,</span> <span class="n">dummy_variable_1</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>

<span class="c1"># drop original column &quot;fuel-type&quot; from &quot;df&quot;</span>
<span class="n">df</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="s2">&quot;fuel-type&quot;</span><span class="p">,</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">1</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[104]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[104]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>aspiration</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>length</th>
      <th>...</th>
      <th>compression-ratio</th>
      <th>horsepower</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
      <th>city-L/100km</th>
      <th>horsepower-binned</th>
      <th>fuel-type-diesel</th>
      <th>fuel-type-gas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>0.811148</td>
      <td>...</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000.0</td>
      <td>21</td>
      <td>8.703704</td>
      <td>13495.0</td>
      <td>11.190476</td>
      <td>Low</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>std</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>0.811148</td>
      <td>...</td>
      <td>9.0</td>
      <td>111</td>
      <td>5000.0</td>
      <td>21</td>
      <td>8.703704</td>
      <td>16500.0</td>
      <td>11.190476</td>
      <td>Low</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>std</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>0.822681</td>
      <td>...</td>
      <td>9.0</td>
      <td>154</td>
      <td>5000.0</td>
      <td>19</td>
      <td>9.038462</td>
      <td>16500.0</td>
      <td>12.368421</td>
      <td>Medium</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>0.848630</td>
      <td>...</td>
      <td>10.0</td>
      <td>102</td>
      <td>5500.0</td>
      <td>24</td>
      <td>7.833333</td>
      <td>13950.0</td>
      <td>9.791667</td>
      <td>Low</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>std</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>0.848630</td>
      <td>...</td>
      <td>8.0</td>
      <td>115</td>
      <td>5500.0</td>
      <td>18</td>
      <td>10.681818</td>
      <td>17450.0</td>
      <td>13.055556</td>
      <td>Low</td>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 29 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The last two columns are now the indicator variable representation of the fuel-type variable. It's all 0s and 1s now.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><b>Create indicator variable to the column of "aspiration": "std" to 0, while "turbo" to 1.</b></p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[105]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;aspiration&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[105]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>std      165
turbo     36
Name: aspiration, dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[106]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dummy_variable_2</span><span class="o">=</span><span class="n">pd</span><span class="o">.</span><span class="n">get_dummies</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;aspiration&quot;</span><span class="p">])</span>
<span class="n">dummy_variable_2</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[106]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>std</th>
      <th>turbo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[107]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># change column names for clarity</span>
<span class="n">dummy_variable_2</span><span class="o">.</span><span class="n">rename</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">{</span><span class="s1">&#39;std&#39;</span><span class="p">:</span><span class="s1">&#39;aspiration-std&#39;</span><span class="p">,</span> <span class="s1">&#39;turbo&#39;</span><span class="p">:</span> <span class="s1">&#39;aspiration-turbo&#39;</span><span class="p">},</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">dummy_variable_2</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[107]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>aspiration-std</th>
      <th>aspiration-turbo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><b>Merge the new dataframe to the original dataframe then drop the column 'aspiration'</b></p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[108]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">=</span><span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">df</span><span class="p">,</span> <span class="n">dummy_variable_2</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="s2">&quot;aspiration&quot;</span><span class="p">,</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[108]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>symboling</th>
      <th>normalized-losses</th>
      <th>make</th>
      <th>num-of-doors</th>
      <th>body-style</th>
      <th>drive-wheels</th>
      <th>engine-location</th>
      <th>wheel-base</th>
      <th>length</th>
      <th>width</th>
      <th>...</th>
      <th>peak-rpm</th>
      <th>city-mpg</th>
      <th>highway-mpg</th>
      <th>price</th>
      <th>city-L/100km</th>
      <th>horsepower-binned</th>
      <th>fuel-type-diesel</th>
      <th>fuel-type-gas</th>
      <th>aspiration-std</th>
      <th>aspiration-turbo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>0.811148</td>
      <td>0.890278</td>
      <td>...</td>
      <td>5000.0</td>
      <td>21</td>
      <td>8.703704</td>
      <td>13495.0</td>
      <td>11.190476</td>
      <td>Low</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>two</td>
      <td>convertible</td>
      <td>rwd</td>
      <td>front</td>
      <td>88.6</td>
      <td>0.811148</td>
      <td>0.890278</td>
      <td>...</td>
      <td>5000.0</td>
      <td>21</td>
      <td>8.703704</td>
      <td>16500.0</td>
      <td>11.190476</td>
      <td>Low</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>122</td>
      <td>alfa-romero</td>
      <td>two</td>
      <td>hatchback</td>
      <td>rwd</td>
      <td>front</td>
      <td>94.5</td>
      <td>0.822681</td>
      <td>0.909722</td>
      <td>...</td>
      <td>5000.0</td>
      <td>19</td>
      <td>9.038462</td>
      <td>16500.0</td>
      <td>12.368421</td>
      <td>Medium</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>four</td>
      <td>sedan</td>
      <td>fwd</td>
      <td>front</td>
      <td>99.8</td>
      <td>0.848630</td>
      <td>0.919444</td>
      <td>...</td>
      <td>5500.0</td>
      <td>24</td>
      <td>7.833333</td>
      <td>13950.0</td>
      <td>9.791667</td>
      <td>Low</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>164</td>
      <td>audi</td>
      <td>four</td>
      <td>sedan</td>
      <td>4wd</td>
      <td>front</td>
      <td>99.4</td>
      <td>0.848630</td>
      <td>0.922222</td>
      <td>...</td>
      <td>5500.0</td>
      <td>18</td>
      <td>10.681818</td>
      <td>17450.0</td>
      <td>13.055556</td>
      <td>Low</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 30 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>save the new csv</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[109]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">to_csv</span><span class="p">(</span><span class="s1">&#39;clean_df.csv&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1>Thank you for completing this notebook</h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><h3>Reference:</h3>
<a href="https://www.bigdatauniversity.com" target="_blank">Cognitive Class</a></p>
<p><a href="https://www.linkedin.com/in/mahdi-noorian-58219234/" target="_blank">Mahdi Noorian PhD</a>, <a href="https://www.linkedin.com/in/joseph-s-50398b136/" target="_blank">Joseph Santarcangelo</a>, Bahare Talayian, Eric Xiao, Steven Dong, Parizad, Hima Vsudevan and <a href="https://www.linkedin.com/in/fiorellawever/" target="_blank">Fiorella Wenver</a> and <a href=" https://www.linkedin.com/in/yi-leng-yao-84451275/ " target="_blank" >Yi Yao</a>.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> 
</pre></div>

    </div>
</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
