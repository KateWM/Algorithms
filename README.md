ALGORITHM analyze_sentence
VAR
    ch           : CHAR;
    length       : INTEGER;
    word_count   : INTEGER;
    vowel_count  : INTEGER;
    in_word      : BOOLEAN;

BEGIN
    length ← 0
    word_count ← 0
    vowel_count ← 0
    in_word ← FALSE

    REPEAT
        Read( ch )
        length ← length + 1

        IF ch IN ['a','e','i','o','u','A','E','I','O','U'] THEN
            vowel_count ← vowel_count + 1
        ENDIF

        IF ch ≠ ' ' AND in_word = FALSE THEN
            word_count ← word_count + 1
            in_word ← TRUE
        ELSE IF ch = ' ' THEN
            in_word ← FALSE
        ENDIF

    UNTIL ch = '.'

    Write("Length of the sentence: ", length)
    Write("Number of words: ", word_count)
    Write("Number of vowels: ", vowel_count)
END
