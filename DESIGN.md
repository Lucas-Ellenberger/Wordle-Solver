# Lucas Ellenberger HW 7 Design Document

## Score Letter

Initialize a counter for the words with the letter

Loop through all words in vocabulary

If the sting at that position is not NULL, as in it hasn't been eliminated

Use strrchr to see if the letter is in vocabulary[i]

If it is in word, increment the counter

return the counter after looping through all words

## Score Word

Initialize a known character array of size 26 (one for each letter) to 0

Initialize a score and a current for later

For each letter in the word, current = (word[i] - 'a'), to make code more readable

If the letter in known[current] is still 0, we haven't included the score

	score += letter_score[current]
	known[current] = 1; // so we don't add the score for the same letter

return the score

## Filter Vocab Gray

Initialize a counter for the number of words filtered

For every word in the vocab:

	If vocab[i] is not NULL // it has not been previously eliminated

		if strrchr(vocab[i], letter) is not NULL // the gray letter is in the word

			free(vocab[i])
			vocab[i] = NULL // so we don't try to access it again
			increment the counter

return the counter

## Filter Vocab Yellow

Initialize a counter for the number of words filtered

For every word in the vocab:

	If vocab[i] is not NULL // it has not been previously eliminated

		If (vocab[i][position] is the letter OR if strrchr(vocab[i], letter) is NULL
		// there is the yellow letter in the same position or the yellow letter is not in the word

			free(vocab[i])
			vocab[i] = NULL // so we don't try to access it again
			increment the counter

return the counter

## Filter Vocab Green

Initialize a counter for the number of words filtered

For every word in the vocab:

	If vocab[i] is not NULL // it has not been previously eliminated

		If (vocab[i][position] is not the green letter):

			free(vocab[i])
			vocab[i] = NULL // so we don't try to access it again
			increment the counter

return counter
