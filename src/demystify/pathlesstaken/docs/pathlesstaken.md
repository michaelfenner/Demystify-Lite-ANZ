```
    Help on module pathlesstaken:

    NAME
        pathlesstaken - pathlesstaken

    FILE
        ../pathlesstaken/pathlesstaken.py

    DESCRIPTION
        Module that implements checks against the Microsoft Recommendations for
        file naming, plus additional recommended analyses documented below.

        First created based on the recommendations here:
            http://msdn.microsoft.com/en-us/library/aa365247(VS.85).aspx

        First available in:
            https://github.com/exponential-decay/droid-siegfried-sqlite-analysis-engine

        class PathlesstakenAnalysis(__builtin__.object)
         |  PathlesstakenAnalysis
         |
         |  Class to encapsulate the functionality that can be accessed via this
         |  module. All functions are documented further below.
         |
         |  Methods defined here:
         |
         |  complete_file_name_analysis(self, string, folders=False, verbose=False)
         |      Run all analyses over a string object. The analyses are as follows:
         |
         |      * detect_non_ascii_characters
         |      * detect_non_recommended_characters
         |      * detect_non_printable_characters
         |      * detect_microsoft_reserved_names
         |      * detect_spaces_at_end_of_names
         |      * detect_period_at_end_of_name
         |
         |  detect_microsoft_reserved_names(self, string)
         |      Detect names that are considered difficult on Microsoft file
         |      systems. There is a special history to these characters which can be
         |      read about on this link below:
         |
         |          * http://msdn.microsoft.com/en-us/library/aa365247(VS.85).aspx
         |
         |  detect_non_ascii_characters(self, string, folders=False)
         |      Detect characters outside of an ASCII range. These are more
         |      difficult to preserve in today's systems, even still, though it is
         |      getting easier.
         |
         |  detect_non_printable_characters(self, string, folders=False)
         |      Detect control characters below 0x20 in the ASCII table that cannot
         |      be printed. Examples include ESC (escape) or BS (backspace).
         |
         |  detect_non_recommended_characters(self, string, folders=False)
         |      Detect characters that are not particularly recommended. These
         |      characters for example a forward slash '/' often have other meanings
         |      in computer systems and can be interpreted incorrectly if not handled
         |      properly.
         |
         |  detect_period_at_end_of_name(self, string, folders=False)
         |      Detect a full-stop at the end of a name. This might indicate a
         |      missing file extension.
         |
         |  detect_spaces_at_end_of_names(self, string, folders=False)
         |      Detect spaces at the end of a string. These spaces if ignored can
         |      lead to incorrectly matching strings, e.g. 'this ' is different to
         |      'this'.
         |

    FUNCTIONS

        main()
            pathlesstaken is a script to identify strings that when interpreted as
            file paths might prove more difficult to look after and preserve. The
            example given previously was special Microsoft reserved names. Other
            examples might include non-ASCII characters in a horrendously ASCII biased
            world.

            Notes: Running this code via main will output the most information possible
            about a string. The function complete_file_name_analysis can be called on
            the module level (or all other analysis functions) with verbose reporting
            turned off if the caller would like to see just the first instance of a
            string that might need additional processing attention, i.e. as a flag that
            there is something to look at.

    DATA
        print_function = _Feature((2, 6, 0, 'alpha', 2), (3, 0, 0, 'alpha', 0)...
        unicode_literals = _Feature((2, 6, 0, 'alpha', 2), (3, 0, 0, 'alpha', ...
```
