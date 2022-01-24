This repository is a research archive and contains everything you need to run my assignment for the course "Introduction to Bayesian Statistics." The PDF file contains the final report. The file manuscript_inan.Rmd contains the script and text. Code-chunks follow after paragraphs in which their relevant content is introduced. The three .csv files are the data files that I use from Our World In Data. To walk through the research project, read the text in the .Rmd file and look at the respective code-chunks. If you do not care about the details, I suggest to just read the PDF file. 

Below is a documentation of what happens at which line of code. I do not suggest to read this part (although it is in the README file), but you can use it if you want to navigate the file in more detail later.  

16-41; 54-64: Data tidying and diagnostics

70-212: The MH- and Gibbs sampler with model fit and convergence, written as a function 
	72-88: set-up for storage
	90-164: sampling
		94-128 chain 1
		94 sample b0
		96-119: sample b1 in MH-step chain 1
			101-104: sampling from proposal distribution
			105-108: assessing density of current and new value
			109-118: computing probability of acceptance, making decision and storing decision for acceptance rate.
		123 sample b2
		126 sample sigma^2
		131-163 repeat procedure for chain 2
	175-183 get sample statistics and MH-error for each chain and for pool of chain
	185-192: write tables for output as dataframe giving sample statistics for each chain and pooled chain
	195-203 compute DIC
		197 compute likelihood for each iteration for DBAR
		200-201: compute dbar and dhat
		203: compute DIC

	205-210: trace plots for convergence as output
	212: output of sampler: both chains and pooled chain, samplestats, acceptance rates, dic.

221-226: Autocorrelation plots for each parameter

231-294: posterior predictive pvalues
	235-276 pvalue for homoscedasticity
		235-239: set up and simulation of datasets
		242: fitted data for each set of parameters
		248-254: compute discrepancy measure for simulated data
		257-263: compute discrepancy measure for observed data
		270-276: compute pvalue
	270-294: pvalue for outliers

297-325: bayes factor using bain package

328-340: DIC comparison of three models

343-366: using model with log(GDP) as explained in discussion
369-445: testing if DIC writing elaborate function with one predictor is same as DIC using function for both predictors where one predictor is a variable with only 0’s
