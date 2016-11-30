{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "from selenium import webdriver"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Start a driver with phantomJS.\n",
    "This is like open phantomJS browser. param is the path for phantomJS. "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "driver = webdriver.PhantomJS('./phantomjs-2.1.1-windows/bin/phantomjs.exe')"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Use method get to open a url"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "driver.get('http://xxx')"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Use find_element_*method to locate elements in web page.\n",
    "To locate the element, F12 in chrome is useful.\n",
    "send_keys to fill in text.\n",
    "click() to click buttons."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "driver.find_element_by_name(\"login\").clear()\n",
    "driver.find_element_by_name(\"login\").send_keys('xxx')\n",
    "driver.find_element_by_name(\"password\").clear()\n",
    "driver.find_element_by_name(\"password\").send_keys('xxx')\n",
    "driver.find_element_by_class_name(\"submit\").click()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "is_enabled can be used to test if button element is still enable."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 23,
   "metadata": {
    "collapsed": false,
    "scrolled": true
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "False"
      ]
     },
     "execution_count": 23,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "driver.find_element_by_xpath('xxx').is_enabled()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Switch to frams by swith_to_frame.\n",
    "Remenber: always call switch_to_default_content after done with a frame"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "driver.switch_to_frame('menuFrame')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "driver.find_element_by_css_selector(\"xxx\").click()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "driver.switch_to_default_content()\n",
    "driver.switch_to_frame('mainFrame')"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Select could use to manipulate with selection elements"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "from selenium.webdriver.support.ui import Select"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 18,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "sel = driver.find_element_by_css_selector('xxx')\n",
    "Select(sel).select_by_value('xxx')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "driver.close()"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python [Root]",
   "language": "python",
   "name": "Python [Root]"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.5.2"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 0
}
