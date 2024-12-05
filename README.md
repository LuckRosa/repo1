package es.unileon.prg1.connections;

import static org.junit.Assert.assertEquals;
import static org.junit.Assert.assertFalse;
import static org.junit.Assert.assertTrue;

import org.junit.Before;
import org.junit.Test;

public class ItemTest {

    private Item item;

    @Before
    public void setUp() {
        this.item = new Item("Gato", Level.EASY);
    }

    @Test
    public void testItem() {
        assertEquals("Gato", this.item.toString());
    }

    @Test
    public void testIsSelected() {
        assertFalse(this.item.isSelected());
    }

    @Test
    public void testSelect() {
        assertFalse(this.item.isSelected());
        this.item.changeIsSelected();
        assertTrue(this.item.isSelected());
    }

    @Test
    public void testDeselect() {
        assertFalse(this.item.isSelected());
        this.item.changeIsSelected();
        assertTrue(this.item.isSelected());
        this.item.changeIsSelected();
        assertFalse(this.item.isSelected());
    }
}
package es.unileon.prg1.connections;

public class Item {
    private String word;
    private boolean selected;
    private Level level;

    public Item(String word, Level level) {
        this.word=word;
        this.selected=false;
        this.level=level;
    }

    public String getWord() {
        return this.word;
    }

    public boolean isSelected() {
        return this.selected;
    }

    public void changeIsSelected() {
        if (this.selected==true) {
            this.selected=false;
        }
        else {
            this.selected=true;
        }
    }

    public Level getLevel() {
        return this.level;
    }

    public boolean isEqual(String word) {
        return this.word==word;
    }

    public String toString() {
        StringBuilder output = new StringBuilder();

        if(this.selected) {
            output.append("-");
            output.append(this.word);
            output.append("-");
        }
        else {
            output.append(this.word);
        }

        return output.toString();
    }
}
﻿
