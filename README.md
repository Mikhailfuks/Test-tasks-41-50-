tasks 41 

public class LeapYearUtil {
    public boolean isLeapYear(int year) {
        return year % 4 == 0 && (year % 100 != 0 || year % 400 == 0);
    }
}

import static org.junit.jupiter.api.Assertions.assertTrue;
import org.junit.jupiter.api.Test;

public class LeapYearUtilTest {
    @Test
    public void testIsLeapYear() {
        LeapYearUtil leapYearUtil = new LeapYearUtil();
        assertTrue(leapYearUtil.isLeapYear(2020));
        assertFalse(leapYearUtil.isLeapYear(2021));
    }
}

tasks 42 


public class CamelCaseUtil {
    public String toCamelCase(String str) {
        StringBuilder camelCase = new StringBuilder();
        for (String word : str.split(" ")) {
            if (word.length() > 0) {
                camelCase.append(Character.toUpperCase(word.charAt(0)))
                         .append(word.substring(1).toLowerCase());
            }
        }
        return camelCase.toString();
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class CamelCaseUtilTest {
    @Test
    public void testToCamelCase() {
        CamelCaseUtil camelCaseUtil = new CamelCaseUtil();
        assertEquals("HelloWorld", camelCaseUtil.toCamelCase("hello world"));
        assertEquals("JavaProgramming", camelCaseUtil.toCamelCase("java programming"));
    }
}





tasks 43 

public class SecondMaxUtil {
    public Integer findSecondMax(int[] array) {
        Integer max = null;
        Integer secondMax = null;
        for (int num : array) {
            if (max == null || num > max) {
                secondMax = max;
                max = num;
            } else if (num != max && (secondMax == null || num > secondMax)) {
                secondMax = num;
            }
        }
        return secondMax;
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class SecondMaxUtilTest {
    @Test
    public void testFindSecondMax() {
        SecondMaxUtil secondMaxUtil = new SecondMaxUtil();
        assertEquals(4, secondMaxUtil.findSecondMax(new int[]{1, 2, 4, 3}));
        assertEquals(null, secondMaxUtil.findSecondMax(new int[]{5, 5, 5})); // Все одинаковые
    }
}



tasks 44 

public class StringSplitUtil {
    public String[] splitIntoWords(String str) {
        return str.split("\s+");
    }
}

import static org.junit.jupiter.api.Assertions.assertArrayEquals;
import org.junit.jupiter.api.Test;

public class StringSplitUtilTest {
    @Test
    public void testSplitIntoWords() {
        StringSplitUtil stringSplitUtil = new StringSplitUtil();
        assertArrayEquals(new String[]{"Hello", "world"}, stringSplitUtil.splitIntoWords("Hello world"));
    }
}


tasks 45 

public class MinMaxUtil {
    public int[] findMinMax(int[] array) {
        int min = array[0];
        int max = array[0];
        for (int num : array) {
            if (num < min) min = num;
            if (num > max) max = num;
        }
        return new int[]{min, max};
    }
}

import static org.junit.jupiter.api.Assertions.assertArrayEquals;
import org.junit.jupiter.api.Test;

public class MinMaxUtilTest {
    @Test
    public void testFindMinMax() {
        MinMaxUtil minMaxUtil = new MinMaxUtil();
        assertArrayEquals(new int[]{1, 5}, minMaxUtil.findMinMax

tasks 46 

public class SpaceUtil {
    public boolean isOnlySpaces(String str) {
        return str.trim().isEmpty();
    }
}

import static org.junit.jupiter.api.Assertions.assertTrue;
import org.junit.jupiter.api.Test;

public class SpaceUtilTest {
    @Test
    public void testIsOnlySpaces() {
        SpaceUtil spaceUtil = new SpaceUtil();
        assertTrue(spaceUtil.isOnlySpaces("    "));
        assertFalse(spaceUtil.isOnlySpaces("  a  "));
    }
}

tasks 47

public class WordCountUtil {
    public int countOccurrences(String str, String word) {
        String[] words = str.split("\s+");
        int count = 0;
        for (String w : words) {
            if (w.equals(word)) {
                count++;
            }
        }
        return count;
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class WordCountUtilTest {
    @Test
    public void testCountOccurrences() {
        WordCountUtil wordCountUtil = new WordCountUtil();
        assertEquals(2, wordCountUtil.countOccurrences("hello world hello", "hello"));
    }
}

tasks 48

public class GeometricProgressionUtil {
    public double geometricProgression(double a, double r, int n) {
        return a * Math.pow(r, n - 1);
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class GeometricProgressionUtilTest {
    @Test
    public void testGeometricProgression() {
        GeometricProgressionUtil progressionUtil = new GeometricProgressionUtil();
        assertEquals(8.0, progressionUtil.geometricProgression(2, 2, 4)); // 2 * 2^(4-1)
    }
}

tasks 49 

import java.util.List;

public class ListToArrayUtil {
    public Integer[] convertToArray(List<Integer> list) {
        return list.toArray(new Integer[0]);
    }
}

import static org.junit.jupiter.api.Assertions.assertArrayEquals;
import org.junit.jupiter.api.Test;
import java.util.List;

public class ListToArrayUtilTest {
    @Test
    public void testConvertToArray() {
        ListToArrayUtil listToArrayUtil = new ListToArrayUtil();
        Integer[] result = listToArrayUtil.convertToArray(List.of(1, 2, 3));
        assertArrayEquals(new Integer[]{1, 2, 3}, result);
    }
}

tasks 50 


public class StringWeightUtil {
    public int calculateWeight(String str) {
        int weight = 0;
        for (char c : str.toCharArray()) {
            weight += (int) c;
        }
        return weight;
    }
}

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class StringWeightUtilTest {
    @Test
    public void testCalculateWeight() {
        StringWeightUtil weightUtil = new StringWeightUtil();
        assertEquals(195, weightUtil.calculateWeight("ABC")); // 65 + 66 + 67
    }
}


